# ChessCommentary

## Project Overview
Language Models, independent of their scales, demonstrated they have the ability to be applied to various downstream tasks. We here explore a somewhat multimodal downstream task of chess commentary. But here we take a shortcut of using PGN notation to convert chessboard and moves into text representation thus converting it to a single modality problem, although suffering from the fact that some models may not interpret PEN notation correctly. 

## Dataset
We fetched multiple chess game records along with commentary for each step. Not every move is accompanied by commentary, and some are in different notations. To keep a full experience, we opted to keep all the steps during our training process.

## Models
We here did two approaches. One is RNN and one is LLM. The idea being since the data we get is PGN/FEN notations, we could process it similar to images. Thus we can keep track of the game states and give it sequential information of how the game is played out for both players. As for LLM, we also feed it with a sequence of all previous moves, and then ask it to produce a commentary of the target step. 

## Using the project
First run 
<pre></pre>
pip install -r requirement.txt
</pre>
We have included scripts for both approaches in our codebase. "EncDecv4.ipynb" contains the RNN approach; "LLMTrain_v1.ipynb" and "LLMTrain_v2.ipynb" contains the finetuning LLM approach. Both produce comparable results, but with hindsight LLM may still be the better choice being more human readable and could generate better commentary even with small dataset due to the common language capability it gained from pretraining.
