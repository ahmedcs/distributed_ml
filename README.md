# distributed_ml
Encoding schemes for communicating gradients in Distributed ML.

Currently this repository consists of six encoding schemes:
1. Run Length Encoding
2. Normal Huffman Encoding
3. Run Length Huffman
4. Sample Huffman
5. Sample Huffman with Sparsity
6. Elias Omega Encoding

Each encoding is  defined in a seperate class, and each class has a compress and a decompress member function. The compress function returns the encoded document and also update the Encoding class object with the encodings and revrerse mapping of the encodings which would later help in decompression. The decompress method decodes the encoded document and returns the decoded document.

The encoding schemes can be seen as an extended unit in the  https://github.com/sands-lab/grace/tree/master/grace_dl/dist/compressor
 of the following github project https://github.com/sands-lab/grace/ of Sands-Lab in KAUST.

An ecoding scheme can be used as follows:

my_scheme = <Encoding_Scheme_Class>()
encoded_document = my_scheme.compress(qunatized_grads)
decoded_document = my_scheme.decompress
code_length_of_encoded_document = my_scheme.code_length
