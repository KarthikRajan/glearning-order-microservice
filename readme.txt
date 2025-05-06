

### Key Steps:
1. **Checkout**: Fetches the source code from GitHub.
2. **Assume AWS IAM Role** via OIDC: Securely authenticates using federated credentials, avoiding hardcoded secrets.
3. **Docker Multi-Stage Build**:
   - Stage 1: Compiles the Java app using Maven and generates a JAR file.
   - Stage 2: Copies the JAR into a minimal Amazon Corretto base image.
4. **Tag & Push to Amazon ECR**.

---88
 IAM Role Setup for GitHub Actions (OIDC)

To allow GitHub Actions to push images to ECR securely, we created a custom IAM Role.
