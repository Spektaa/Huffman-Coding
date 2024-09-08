# Huffman Coding - Data Compression Project

## Background

Data compression has revolutionized digital multimedia. Compression algorithms reduce the size of a file while ensuring that files can be fully restored to their original state if needed. A wide range of algorithms can be used for lossless data compression, one of the simplest being Run-Length Encoding (RLE). However, RLE's major drawback is that if there are no repeated characters, the output size can be double that of the input. To address this issue, **Huffman Coding** was introduced by David Huffman.

Huffman coding is a more successful method for data compression. It creates shorter binary codes for more frequently occurring characters, making it highly efficient in reducing file sizes.

## Purpose

Every piece of information in computing is encoded as strings of 1’s and 0’s. The main purpose of information theory is to convey information in as few bits as possible, ensuring every encoding is unambiguous. **Huffman coding** achieves this by assigning fewer bits to frequently occurring characters, thus reducing the overall length of the data and improving compression efficiency.

## Objectives

- Compress data without any loss of information.
- Utilize statistical coding: more frequent symbols have shorter code words.
- Transmit information using as few bits as possible.
- Use variable-length encoding, i.e., variable bits for encoding.

## Scope

In the modern era, data transmission over the Internet depends heavily on time. More data takes longer to transmit. **Huffman coding** reduces the data size, which in turn significantly reduces the transmission time. This algorithm is widely used for lossless data encoding in various applications, such as:

- Data compression tools like **GZIP** and **PKZIP (WinZip)**.
- Image formats such as **JPEG** and **PNG**.
- Compression algorithms like **DEFLATE**.
- Embedded processor code compression techniques.
- Advanced audio coding standards.

## How It Works

The Huffman coding algorithm consists of two main steps:

1. **Building the Huffman Tree** from input characters.
2. **Traversing the Huffman Tree** to assign binary codes to each character (encoding).

## Decompression (Decoding)

To decompress the data, the Huffman tree must be reconstructed. One approach stores the encoding map (containing characters and their frequency count) along with the encoded data, but this can result in significant overhead. Instead, a more efficient approach is used, where the tree is reconstructed using a **preorder traversal**:

- Non-leaf nodes are marked with `0`.
- Leaf nodes are marked with `1` and store the corresponding character.

This method takes fewer bytes to store the Huffman tree structure, making it more efficient.

## Time Complexity

The time complexity of the Huffman coding algorithm is:

- Extracting the minimum frequency from the priority queue (using `extractMin()`) is called `2 x (n-1)` times for `n` nodes.
- Since `extractMin()` uses a min-heap (`minHeapify()`) with complexity `O(log n)`, the overall time complexity of Huffman coding is **O(n log n)**, where `n` is the number of unique characters in the input text.

## Conclusion

Though various algorithms exist for data compression, **Huffman Coding** stands out for lossless data compression. It employs a greedy approach to efficiently encode data into shorter representations, maintaining all the original information. It's simple, efficient, and widely used in real-world applications.
