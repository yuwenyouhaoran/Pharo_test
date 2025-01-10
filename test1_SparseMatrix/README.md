Test unit

This code demonstrates a complete process for converting a traditional matrix (in the form of a 2D array) into a sparse matrix representation and verifying the correctness of the transformation. First, a traditional matrix traditionalMatrix is defined. It is then encoded into a sparse matrix representation using the encodeFromTraditionalMatrix: method, and the encoded result is printed. Next, the sparse matrix is decoded back into the traditional matrix format using the decodeToTraditionalMatrix:rows:cols: method, and the decoded result is printed. Finally, the restored matrix is compared with the original matrix, and the test results are printed to verify the correctness of the encoding and decoding process of the sparse matrix.

'''
| traditionalMatrix sparseMatrix decodedMatrix testResult |
traditionalMatrix := #( #(1 0 0 0)
                        #(0 2 0 0)
                        #(0 0 3 0)
                        #(0 0 0 4) ).

sparseMatrix := SparseMatrix new encodeFromTraditionalMatrix: traditionalMatrix.
Transcript show: 'Encoded Sparse Matrix: ', sparseMatrix printString; cr.

decodedMatrix := SparseMatrix new decodeToTraditionalMatrix: sparseMatrix rows: 4 cols: 4.
Transcript show: 'Decoded Matrix: ', decodedMatrix printString; cr.

testResult := (traditionalMatrix = decodedMatrix).
testResult
    ifTrue: [ Transcript show: 'Test Passed: The decoded matrix matches the original!'; cr ]
    ifFalse: [ Transcript show: 'Test Failed: The decoded matrix does not match the original!'; cr ].
'''
