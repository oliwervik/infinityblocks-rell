<!--
 Copyright (c) 2024 Oliwer Svensson (oliwervik)

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
 GNU General Public License for more details.

 You should have received a copy of the GNU General Public License
 along with this program. If not, see <https://www.gnu.org/licenses/>.
 -->

# Infinityblocks
A collaborative art project on the Chromia blockchain.

This is a [Next.js](https://nextjs.org/) project with Material UI and [PiXI JS](https://pixijs.com/) html engine.

## Before you start

Start by setting up your local environment. Follow the steps on the official chromia docs.

https://docs.chromia.com/category/set-up-local-environment

## How to use

1. [Clone the client repo](https://github.com/oliwervik/infinityblocks):

2. Install and run:

    ```bash
    npm install
    npm run dev
    ```

3. [Clone the rell blockchain repo](https://github.com/oliwervik/infinityblocks-rell)

4. Install library dependencies

    ```bash
    chr install
    ```

5. Generate a secret

    ```bash
    chr keygen --save .secret
    ```

6. Update `line 12` `"admin_pubkey"` in chromia.yml to your new generated public key

7. Start the node
    
    ```bash
    chr node start --wipe
    ```

8. Run chromia tx to initialize the canvas (see [main.rell](https://github.com/oliwervik/infinityblocks-rell/blob/main/src/main.rell))

    ```bash
    chr tx init --secret .secret --await 
    ```

9. Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

10. Install metamask extension to your browser and click "Login to view canvas" to create an account and sign in.

## Good to know commands
```python
chr tx init --secret .secret --await     

chr query get_all_cells user_id=x'0'

chr tx  --secret .secret --await admin.canvas.update_canvas_zoomScale 0.4 10

chr tx admin.wallet.give_tokens 'account_id=x'ACCOUNT_ID' 'amount=50' --secret .secret --await

chr query get_leaderboard_participants 'type=0' 'page_size=10'
```