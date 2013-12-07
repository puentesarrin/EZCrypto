EZCrypto
==========

Easy to use wrapper around cryptographic libraries for Python.

## Usage examples ##

### Importing the RSA PrivateKey class

    from ezcrypto.pki.rsa import PrivateKey

### Generating a new key ###

    private_key = PrivateKey.generate()

### Loading a private key from a PEM file

    private_key = PrivateKey.load_from_pem_file('/path/to/priv.pem')   

### Obtaining the public key ###

    public_key = private_key.get_public_key()

### Loading a public key from a PEM file

    public_key = PublicKey.load_from_pem_file('/path/to/pub.pem')

### Exporting a public/private key as a PEM string ###

    my_key.export_as_pem()

### Creating a private key instance from a PEM string ###

    private_key = PrivateKey(pem)
 
### Encrypting data of arbitrary length as Base64 ###

    data = my_key.encrypt_as_base64(data)

### Decrypting data from Base64 ###

    data = my_key.decrypt_from_base64(data)

### Signing a message using a private key ###

    signature = private_key.sign(message)

### Verifying a message signed with a private key ###

    private_key.verify(message, signature)

### Signing the hash of a message using a private key ###

    signature = private_key.sign_after_hashing(message)

### Verifying the hash of a message signed with a private key ###

    private_key.verify_after_hashing(message, signature)


NOTES: 

* EZCrypto uses PyCrypto for all cryptographic operations.
* Hashing is made using the SHA1 function from Python's hashlib standard module.

(c) 2012-2013 - Antonio Ognio <antonio@ognio.com>
