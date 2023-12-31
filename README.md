# FUTO Photos
This is the web interface for the FUTO Photos cloud storage application.

FUTO Photos is an end-to-end encrypted cloud storage app that
that enables users to securely store their photos and videos while safeguarding
security and privacy.
The mobile app for android recently started development with a proof of concept being 
internally released. This interface is synced with the [Circles](https://circu.li/circles.html)
"Photos" room in the gallery.
FUTO Photos is built on Matrix, and as such, it inherits many nice
properties from Matrix, including:

Federation - Anyone can run their own server, and users on different servers can communicate with each other seamlessly.
Open APIs and data formats - FUTO Photos uses standard Matrix message types, and it works
with any spec-compliant Matrix server.
Security - FUTO Photos offers the same security guarantees as Matrix, using the same
E2E encryption code as in Element and other popular Matrix clients.

Note: The current version of this project is only internally accessible by FUTO on gitlab with plans to open-source in the future as all FUTO projects are. I've received permission, however, to display this project on my profile.

# Current Features
User Login and Authentication
- Implementation of the [swiclops](https://gitlab.futo.org/cvwright/swiclops) authentication flows
     - Username and password validation/verification
     - [BS-SPEKE](https://gitlab.futo.org/cvwright/Cbsspeke/-/blob/main/Sources/Cbsspeke/bsspeke.c) (Blind-Salt adaptation of [SPEKE](https://en.wikipedia.org/wiki/SPEKE#:~:text=SPEKE%20is%20one%20of%20the,with%20a%20constant%20gq.) ) cryptographic password verification
- Essential upload, delete, and display functionality
    - Fetching of existing files from "Photos" room on server and displays to /photos home screen
    - Uploading of x number of files to "Photos" room on server followed by display update
    - Syncing of files in a Circles account for cross-platform and application access
    - Enlarging of files by clicking on them with custom routes setup and planned image view/edit options
    - Deletion of files by sending deletion event to "Photos" room on server followed by display update

# Quickstart
## Development Quickstart
Note: Currently the fetch and upload files functionality only supports unencrypted rooms, 
use this test account created with unencrypted rooms to see all features in action - 
- Username: testphotos3 
- Domain: varun.circles-dev.net 
- Password: swole

Once file encryption is implemented, you can use the [Circles Web Interface](https://gitlab.futo.org/varun/circles-web-interface) or the [Circles app](https://circu.li/circles.html) to create an account and login to
FUTO Photos.

```
# open a shell/terminal and navigate to the desired folder to clone the repository
git clone https://gitlab.futo.org/varun/futo-photos-web.git

# navigate to the newly created project directory
cd futo-photos-web

# install dependencies needed to run the project in the root folder of the project
npm install

# run the development server
npm run dev
```

## Build for production
```
# Follow the same steps as above (Development Quickstart) except for npm run dev
npm run build 
```

# FUTO
This project is a product of [FUTO](https://futo.org/). FUTO is an organization dedicated to developing, both through in-house engineering and investment, technologies that frustrate centralization and industry consolidation. FUTO aims to develop and fund open-source tech that gives you back privacy and control.

