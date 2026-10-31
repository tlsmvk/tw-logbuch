# Torwart-Logbuch

Eine Web-App (PWA) für das Handball-Torwarttraining. Die Daten liegen nur lokal im Browser des Geräts (localStorage). Backups laufen über JSON-Export und -Import.

## Auf das Handy bringen (kostenlos, z. B. mit GitHub Pages)
1. Auf github.com ein neues öffentliches Repository anlegen, z. B. `tw-logbuch`.
2. „Add file → Upload files“ wählen und alle Dateien aus dem ZIP hochladen (index.html, sw.js, manifest.webmanifest, die Icons).
3. Unter Settings → Pages: Source „Deploy from a branch“, Branch `main` und Ordner `/ (root)` wählen.
4. Nach etwa einer Minute ist die App unter https://<name>.github.io/tw-logbuch/ erreichbar.
5. iPhone: In Safari öffnen, dann Teilen → „Zum Home-Bildschirm“. Android: In Chrome öffnen, dann ⋮ → „App installieren“.

Alternativ geht jeder Webspace mit HTTPS (z. B. Netlify Drop: den Ordner per Drag-and-drop hochladen).

## Datenformat (JSON v1)
```
{ app:"tw-logbuch", version:1,
  settings:{ teams:[string], categories:[{id,name,group,archived}] },
  keepers:[{id,name,team,year,active,notes:[{id,date,text}]}],
  trainings:[{id,date:"YYYY-MM-DD",time,place,team,topic,plan,review,
              attendance:{keeperId:"da"|"ent"|"unent"|"verl"},
              ratings:{keeperId:{cats:{categoryId:1..5},note}} }] }
```
