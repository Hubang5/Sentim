/**
 * analyzeSentiment
 * 
 * Analyzes the sentiment of a given text.
 * 
 * @param {string} text - The text to analyze.
 * 
 * @returns {number} - A number between -1 and 1 representing the sentiment of the text.
 *  -1 is very negative, 0 is neutral, and 1 is very positive.
 */
const analyzeSentiment = (text) => {
  // Import necessary libraries
  const natural = require('natural');
  const Sentiment = require('sentiment');

  // Initialize sentiment analyzer
  const sentiment = new Sentiment();

  // Tokenize the text
  const tokens = natural.PorterStemmer.tokenizeAndStem(text);

  // Analyze the sentiment of the text
  const result = sentiment.analyze(tokens);

  // Return the sentiment score
  return result.score;
};
