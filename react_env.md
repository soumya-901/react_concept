## PREDEFINED ENV
`process.env.NODE_ENV` for npm start it value "development" and for npm run build "production".
- You cannot override NODE_ENV manually.

`process.env.PUBLIC_URL` is set to the base URL of the application.

- It is useful for resolving assets' paths, especially in production when the app might be served from a subdirectory.

`process.env.TZ` is a system environment variable that holds the current time zone setting.
## SET ENV IN SCRIPT
###  You must create custom environment variables beginning with REACT_APP_
Windows (cmd.exe)

```bash
  set "REACT_APP_NOT_SECRET_CODE=abcdef" && npm start
```
Windows (powershell)

```bash
  ($env:REACT_APP_NOT_SECRET_CODE = "abcdef") -and (npm start)
```
Linux, macOS (Bash)

```bash
  REACT_APP_NOT_SECRET_CODE=abcdef npm start
```

## SET MULTIPLE ENV FILES

- `.env`: Default
- `.env.local`: Local overrides. This file is loaded for all environments except test.
- `.env.development`, `.env.test`, `.env.production`: Environment-specific settings.
- `.env.development.local`, `.env.test.local`, `.env.production.local`: Local overrides of environment-specific settings.

### Priority order of env files
- npm start: `.env.development.local`, `.env.local`, `.env.development`, `.env`
- npm run build: `.env.production.local`, `.env.local`, `.env.production` , `.env`
- npm test: `.env.test.local`, `.env.test`, `.env` (note .env.local is missing)

## Reference

 [For more information](https://create-react-app.dev/docs/adding-custom-environment-variables/)
