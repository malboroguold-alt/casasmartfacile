# GUIDA: Configurazione Facebook OAuth per n8n

## PASSO 1: Crea App su Facebook Developers

1. Vai su https://developers.facebook.com/
2. Accedi con lo stesso account della pagina CasaSmartFacile
3. Clicca "My Apps" → "Create App"
4. Seleziona tipo: **"Business"**
5. Nome app: "CasaSmartFacile Auto"
6. Email: la tua email

## PASSO 2: Aggiungi Prodotti

1. Nel dashboard app, clicca **"Add Product"**
2. Cerca e aggiungi **"Facebook Login"**
3. Cerca e aggiungi **"Pages"**

## PASSO 3: Configura OAuth

1. Vai su Settings → Basic
2. Copia **App ID** e **App Secret** (servono dopo)
3. Vai su Facebook Login → Settings
4. Aggiungi Valid OAuth Redirect URIs:
   ```
   http://TUO-IP-VPS:5678/rest/oauth2-credential/callback
   ```
5. Salva

## PASSO 4: Ottieni Page Access Token

1. Vai su Tools → Graph API Explorer
2. Seleziona la tua app dall'app dropdown
3. Clicca "Get Token" → "Get Page Access Token"
4. Seleziona la pagina "CasaSmartFacile"
5. Copia il token generato (inizia con EA...)

## PASSO 5: Configura n8n

1. Accedi a n8n: `http://TUO-IP-VPS:5678`
2. Username: admin | Password: admin123
3. Vai su Settings → Credentials
4. Clicca "Add Credential"
5. Cerca "Facebook Graph API"
6. Inserisci:
   - App ID: [quello copiato]
   - App Secret: [quello copiato]
   - Access Token: [quello della pagina]
7. Salva

## PASSO 6: Importa Workflow

1. Scarica il file `n8n-workflow-facebook.json`
2. In n8n: Workflows → Import from File
3. Seleziona il file scaricato
4. Attiva il workflow (toggle ON)

## FATTO! 🎉

Ora io posso generare post automaticamente e n8n li pubblicherà da solo!
