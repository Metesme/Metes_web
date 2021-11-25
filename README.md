# Metes_web
Metes is a distributed storage project built on IPFS + Crust. Compared with other similar projects, we have implemented end-to-end encryption. Others cannot obtain the real file when the files CID is leaked. Each file corresponds to a decryption key, and the server will not store the user password and file key, which can prevent library collision and resist relevant review
# Details
1.User registration generates a unique private key for the user, which we call master Key, encrypts the password the user enters with MD5 encryption, encrypts the master Key with the encrypted user password, generates an RSA pair, and encrypts the RSA private key with MasterKey as the key

2.Users log on using the MD5 encrypted user password to decrypt the master key, then use the master key to decrypt the RSA private key, and then use the RSA private key to decrypt the server to encrypt the Token using the RSA public key

3.When a user uploads a file, a fileKey is generated on the client to encrypt the file and stored in the cloud using the master key to encrypt the fileKey.

4.The user decrypts the fileKey through masterKey while downloading, and decrypts the file in fetch through fileKey.
# Milestone 1 Metes-Core functions
| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 1. | Basic User Module  | We will design a safe and fast non-password authentication |  
| 2. | Encrypted Upload Module| We will create a Encrypted Upload that will implement encryption on the client and then upload |  
| 3. | Decryption Download Module | We will create a Crust module that will decrypt on client during download | 


![images](https://github.com/Metesme/Metes_web/blob/main/doc/img/1.gif?raw=true)
![images](https://github.com/Metesme/Metes_web/blob/main/doc/img/2.gif?raw=true)
![images](https://github.com/Metesme/Metes_web/blob/main/doc/img/3.gif?raw=true)
