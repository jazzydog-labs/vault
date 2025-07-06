# Example Snippets

## Schema Definition
```yaml
# schemas/user/v1.yaml
id: User
properties:
  id:
    type: string
  email:
    type: string
    format: email
  created_at:
    type: string
    format: date-time
required:
  - id
  - email
```

## Python Secret Helper (optional)
```python
# tools/secret_helper.py
import os
from cryptography.fernet import Fernet

class SecretHelper:
    def __init__(self, key_env="VAULT_KEY"):
        key = os.environ[key_env].encode()
        self.fernet = Fernet(key)

    def decrypt(self, ciphertext: bytes) -> str:
        return self.fernet.decrypt(ciphertext).decode()

    def encrypt(self, plaintext: str) -> bytes:
        return self.fernet.encrypt(plaintext.encode())
```
This helper might live in a separate secrets repository if Vault decides not to own secret management.
