# Notes

## Important notes

- Added `"resolveJsonModule": true` and `"allowSyntheticDefaultImports": true` to `tsconfig.json` for importing te assets/menu.json

## Architecture

Ranger les composant dans le dossier `in`.

## Scripts

- Build the app, create version file and move the app and the manifest to the wamp server:
  ```bash
  rm -rf ./.angular && nvm use 14 && npm link sb-shared-lib && ng build --configuration production --output-hashing none --base-href="/learn/" && cp manifest.json dist/symbiose/ && zip -r ./web.app dist/symbiose/* && cat web.app | md5sum | awk '{print $1}' > version && cp version dist/symbiose && rm -rf /mnt/c/wamp64/www/equal/public/learn && cp -r dist/symbiose /mnt/c/wamp64/www/equal/public/learn && cp version /mnt/c/wamp64/www/equal/packages/learn/apps/learn && cp manifest.json /mnt/c/wamp64/www/equal/packages/learn/apps/learn && cp web.app /mnt/c/wamp64/www/equal/packages/learn/apps/learn 
  ```
