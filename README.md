:
  schedule:
    - cron: '0 */6 * * *'  # Mỗi 6 giờ
  workflow_dispatch:

jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v3

      - name: Run update script
        run: |
          pip install openai flask
          python server.py
