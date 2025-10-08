# Streamlit AI assistant &mdash; a documentation chatbot for Streamlit

Ever wanted to chat with the Streamlit documentation? Well, with the power of
[Snowflake Cortex](https://docs.snowflake.com/en/guides-overview-ai-features?utm_source=streamlit&utm_medium=referral&utm_campaign=streamlit-demo-apps&utm_content=streamlit-assistant)
now you can!

You can try out the AI Assistant app below:

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://demo-ai-assistant.streamlit.app/)

## Running it yourself

### Snowflake backend setup

1. Open the worksheet at `snowflake/initial_setup.sql` in Snowflake and run it.

1. Open the notebook at `snowflake/populate_st_assistant_data.ipynb` in Snowflake and follow the
   instructions in there.

### Try the app on your machine

1. Get the code:

   ```sh
   $ git clone https://github.com/streamlit/demo-ai-assistant
   ```

1. Start a virtual environment and get the dependencies (requires uv):

   ```sh
   $ uv venv
   $ .venv/bin/activate
   $ uv sync
   ```

1. Add your Snowflake account to `.streamlit/secrets.toml` under `[connections.snowflake]`

   ```toml
   [connections.snowflake]
   account = "YOUR_ACCOUNT_GOES_HERE" # <-- Change this
   # This is the user we set up for you in the pipeline setup steps:
   user = "ST_ASSISTANT_USER"
   # In the Snowflake UI, create an API token for the user above and paste here:
   password = "PASTE_TOKEN_HERE" # <-- Change this
   # Everything below was already set up in the pipeline steps:
   role = "ST_ASSISTANT_USER"
   warehouse = "COMPUTE_WH"
   database = "ST_ASSISTANT_DEV"
   schema = "PUBLIC"
   ```

1. Start the app:

    ```sh
    $ streamlit run streamlit_app.py
    ```
