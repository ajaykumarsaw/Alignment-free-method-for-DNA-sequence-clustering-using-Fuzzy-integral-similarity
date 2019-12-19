# Alignment-free-method-for-DNA-sequence-clustering-using-Fuzzy-integral-similarity
Sequence Similarity tools

 

# format of the DNA sequence file is as follow: Odd line contains sequence names and even line contains DNA sequences (eg:-11linedata.fas)

# check the maximum length among the  DNA sequences and add 10 more array in maximum length in program.

$ wc -L 11linedata.fas 
336 11linedata.fas
# here maximum length of among 11linedata.fas DNA sequences is 336. Therefore assign maximum length in program = 336 + 10= 346

# first run executable file as follow and you will get instruction related to input file and follow instruction:

$ ./feature_extraction
Enter Two arguments. 1_path_of_input_file  2_maximum_length_among_DNA_sequences

$ ./feature_extraction  11linedata.fas  346 > feature_extraction.txt


$ ./arrange_feature_extraction
Enter Two arguments: 1_path_of_input_file 2_number_of_DNA_sequences

$ ./arrange_feature_extraction feature_extraction.txt  11 > arrange_feature_extraction.txt


$ ./similarity
Enter Two arguments: 1_path_of_input_file  2_number_of_DNA_sequences


$ ./similarity  arrange_feature_extraction.txt  11 > similarity.txt


$ ./optimal_order
Enter Two arguments: 1_path_of_input_file  2_number_of_DNA_sequences


$./optimal_order  similarity.txt 11 > optimal_order.txt 

# In above program: we get optimal order k, which we used in next program.

$ ./phylip
Enter Five  arguments: 1_number_of_DNA_sequences  2_maximum_length_among_DNA_sequences 3_optimal_order_k 4_input_path_file 5_sequence_file


$ ./phylip  11 346 8 similarity.txt  11linedata.fas  > phylip.txt

# put in phylip package and used UPGMA approach, you will get phylogenetic tree. Details discussionare  given in Result section of the paper.



