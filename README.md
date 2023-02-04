# Kumaragunachandrarajamahanti_HW2
The function bpe_encrypt takes two arguments: actual_tokens and corpus_data.
The actual_tokens argument is a list of tokens, which are usually strings representing words or sub-words.
The corpus_data argument is a dictionary that maps pairs of tokens to their frequency of occurrence in a corpus.
The function converts the input actual_tokens into a new representation using the Byte Pair Encoding (BPE) algorithm. Here's how it works:
If actual_tokens is a list of length 1, it returns actual_tokens unchanged.
Otherwise, it converts actual_tokens into a list of characters and sets it as the token variable.
The function then enters into an infinite loop.
Within the loop, it calls the function get_possible_pairs to get all possible pairs of consecutive characters in token.
For each pair, the function checks if it exists in the corpus_data dictionary. If it does, the function adds it to a new dictionary bpe_pairs with its frequency of occurrence as the value.
If bpe_pairs is empty, it means there are no pairs in the corpus_data and the loop breaks.
If bpe_pairs is not empty, the function selects the pair with the highest frequency of occurrence and calls the function generate_new_token to merge it into a single character.
The process repeats from step 4 until there are no pairs left in the corpus_data.
Finally, the function returns the new token list as the BPE-encoded representation of actual_tokens.
The function get_possible_pairs takes a single argument word which is a list of characters.
The function generates all possible pairs of consecutive characters in word and returns the resulting set of pairs.
Here's how it works:
The function creates an empty set pairs to store the generated pairs.
It sets the first character in word as prev_char.
The function then iterates through the rest of the characters in word, starting from the second character.
For each character char, the function adds a tuple (prev_char, char) to the set pairs.
The variable prev_char is updated to the current char so that it can be used as the first character in the next iteration.
The function continues to iterate until all characters in word have been processed.
Finally, the function returns the set of pairs.
The generate_new_token function takes two inputs: input_word and character_pair.
character_pair is a tuple containing two characters, and input_word is a string.
The function starts by extracting the two characters from character_pair and assigning them to first_char and second_char.
It then initializes an empty list called output_word to store the new token.
The function then enters a while loop with index as the loop variable. The loop continues as long as index is less than the length of input_word.
In the loop, the function tries to find the index of the first occurrence of first_char in input_word starting from index using the index method. If it finds it, it appends the substring of input_word from index to the found char_index to output_word.
If it can't find the first character, it appends the remaining part of input_word to output_word and breaks out of the loop.
After finding the index of the first character, the function checks if the next character is equal to second_char. If it is, the function appends the string formed by concatenating first_char and second_char to output_word and increments index by 2.
If the next character is not equal to second_char, the function appends only first_char to output_word and increments index by 1.
Finally, after the loop is done, the function returns the output_word list.
