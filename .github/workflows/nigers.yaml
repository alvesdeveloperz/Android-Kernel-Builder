name: CI Debug

on: workflow_dispatch  # Change this from [push] to avoid auto-triggers (optional)

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4

    - name: Install tmate manually
      run: |
        sudo apt update
        sudo apt install -y tmate

    - name: Create public tmate session
      run: |
        tmate -S /tmp/tmate.sock new-session -d
        tmate -S /tmp/tmate.sock wait tmate-ready
        echo "tmate SSH: $(tmate -S /tmp/tmate.sock display -p '#{tmate_ssh}')"
        echo "tmate Web: $(tmate -S /tmp/tmate.sock display -p '#{tmate_web}')"

    - name: Keep session alive
      run: sleep 999999
