# The Basics of Encryption

## Approaches to encryption

There are two main approaches to encryption. _encryption at rest_ and _encryption in transit_.

###### Encryption at rest

This concept refers to encryption in data storage. For example, a laptop encrypting its data. Any data that is written to the internal storage is encrypted, and decrpted when being read.

The method of encryption and decryption is done using a 'secret' that only the laptop owner knows. Normally a password or something similar, and the data used to encrypt other data is derived from this password.

This is beneficial because if the laptop was stolen, the thief wouldn't be able to access the data without the 'secret' required to decrypt that data.

This is a vital part of cloud computing. Users are often using _shared hardware_ due to resource pooling. As a result, user data is normally encrypted at rest to protect it from maliscious attacks.

###### Encryption in transit

This method of encryption is used to protect data when it's travelling somewhere else. An example of this is when you communicate with a bank.

When you send data to a bank, it is encrypted on your side before travelling to the bank where it is decrypted by the bank. When travelling, this communication is enclosed by an 'encryption wrapper' or tunnel which protects the raw data. ANyone peaking at this transfer from the outside would simply see a stream of scrambled data.

## Encryption concepts

There are a few important terms to understand surrounding encryption:

- **Plaintext -** Refers to unencrypted data. This can be text - but it _does not have to be_.
- **Algorithm -** A piece of maths that takes plaintext and an encryption key and encrypts the data.
- **Key -** Combined with plaintext in an algorithm, it generates the encrypted output.
- **Ciphertext -** The encrpyted data. Like plaintext, it can refer to text but any other types of data that can be encrpyted.

## Symmetric encryption

Symmetric encryption is a particular type of encryption process that uses a symmetric key.

In short, this method of encryption is where the plaintext is encrypted using a consistent algorithm before being sent to the receiver. The receiver can then decrypt the ciphertext using the same key and the same algorithm.

However, this presents issues in transporting the key. How can we securely have both parties receive the key? This is why symmetric encryption is typically used for local file storage, where this symmetric key is easily shared between the two trusted parties.

## Asymmetric encryption

In comparison to symmetric encryption, this is much easier to share keys. The two pparties agree to use the same _asymmetric algorithm_ to encrypt and decrypt their data.

Then, they will creat asymmetric encryption keys. These keys are formed of two parst -  a public and a private key.

In this case, the public key can **only** be used to create ciphertext, whilst the private key is required to decrypt the data. The sender will download the recipient's public key to encrypt their data. The sender will then be able to use their private key to decrypt the data into the plaintext.

The reason this is not always used is because it is _very_ computationally expensive. Instead, often asymmetric encryption is used to transmit a symmetric key to then complete symmetric encryption.
