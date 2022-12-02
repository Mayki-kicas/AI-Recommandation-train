# NLP Dijkstra
The goal of the project is to retrieve the sentence from an audio file, determine the start and destination of the path using NLP and finally find the shortest path using the Dijkstra algorithm.

## Speech to text
`python3 speechToText.py`
Records as long as it detects speech.
Contains all the recordings converted in .txt.

## NLP
Use of the space V3 library to detect in a sentence the departure and destination of a train trip.
Model trained on the ./asset/SpeechDestination.csv file, with a scale of 0.8, i.e. for the moment 50 sentences for the train dataset and the rest of the sentences for the test dataset.
The same project was done with spacy V2, however the success rate is lower.
Currently the best model in v3 has a success rate of 93%. Need more samples in the initial dataset.

## Dijkstra
After having created a dataset ./dijkstra/ClearData.csv with our columns departure and arrival well distinct compared to the file ./timetables.csv, we create a graph whose points are the distinct stations of the dataset and whose weights of our stops are the duration of the journey between the 2 stations.