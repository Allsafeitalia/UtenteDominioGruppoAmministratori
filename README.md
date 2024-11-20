# Aggiungere un Utente di Dominio al Gruppo degli Amministratori Locali su Windows 11 Pro

Questa guida spiega come rendere un utente di dominio amministratore locale su un computer Windows 11 Pro. Segui i passaggi per garantire i giusti privilegi all'utente richiesto.

## Requisiti

- Accesso al computer con un utente che abbia privilegi amministrativi.
- Utente di dominio da promuovere ad amministratore locale.

## Passaggi

1. **Accedi al computer** con un account amministratore locale.

2. **Apri il Prompt dei Comandi** come amministratore:
   - Premi `Win + S` e cerca "cmd".
   - Fai clic con il tasto destro su "Prompt dei comandi" e seleziona "Esegui come amministratore".

3. **Esegui il comando per aggiungere l'utente al gruppo degli amministratori locali**. Utilizza il comando seguente:

   ```cmd
   net localgroup Administrators dominio\nomeutente /add
   ```

   Sostituisci:
   - `dominio` con il nome del dominio.
   - `nomeutente` con il nome dell'utente da aggiungere.

   Esempio:

   ```cmd
   net localgroup Administrators azienda\marco /add
   ```

4. **Verifica l'aggiunta**:
   - Per verificare che l'utente sia stato aggiunto al gruppo degli amministratori locali, esegui il comando seguente:

   ```cmd
   net localgroup Administratori
   ```

   Questo comando elencherà tutti i membri del gruppo degli amministratori locali.

## Nota Importante

Il nome del gruppo degli amministratori locali potrebbe variare a seconda della lingua del sistema operativo. Su sistemi in lingua inglese, il gruppo è chiamato `Administrators`, mentre su quelli in italiano è chiamato `Administratori`. Utilizza il comando `net localgroup` per elencare i gruppi disponibili e trovare il nome corretto.

## Risoluzione dei Problemi

- Se il gruppo locale specificato non esiste, esegui il comando seguente per vedere tutti i gruppi locali disponibili:

  ```cmd
  net localgroup
  ```

  Identifica il gruppo amministratori e utilizza il suo nome corretto nel comando di aggiunta.

## Contributi

Sentiti libero di creare un fork di questo repository e aprire una pull request per migliorare questa guida.

## Licenza

Questo progetto è rilasciato sotto la licenza MIT. Consulta il file `LICENSE` per maggiori dettagli.
