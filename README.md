# streamlit-auth-test

Test Google OAuth login on streamlit app

Using code from [here](https://towardsdatascience.com/implementing-google-oauth-in-streamlit-bb7c3be0082c)
but using `st.session_state` rather than the session_state script linked to.

RESULT: it seems to be working as intended. Some things to note:

- This will be a login link from the app itself, not a "login wall".
- If creating OAuth client and keys in GCP as "Internal", only `@coop.no` email holders can access the page.
- The `httpx-oauth` package seems a bit risky to use wrt. long-term stability. It has only 59 stars per
16 June 2022 and a single maintainer.
- The code should be modularised somehow. The simplest is possibly to move all dashboard logic
(to which the user should get access to after succesful login) into modules, and then import those as
a `main` function in `app.py`.
