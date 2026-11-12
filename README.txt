BookingApp — Final Project
Group: SE-2513
Team: Allazhar Aldongarov, Dias Serikov, Yerkenov Abylay

LIVE WEBSITE: https://aishhko-final.vercel.app
REPOSITORY: https://github.com/jjestar/final-web-frontend

PURPOSE
A responsive travel website for comparing illustrative hotel stays and planning
a demo trip. This project is entirely static HTML, CSS and JavaScript.
There is no backend, database server, real reservation, payment or email delivery.

RUN LOCALLY
Use a static server from this folder, for example:
  python -m http.server 8124 --bind 127.0.0.1
Then open http://127.0.0.1:8124/
No npm installation, build command or API key is required.
HTTPS or localhost is recommended for the browser's password hashing API.
Internet is needed only for Open-Meteo weather. All photos, icons, styles and
application scripts are local; the rest of the site works if the weather fails.

NINE CONNECTED PAGES
index.html          Home, destination search, FAQ, saved newsletter preference
search-results.html Live search, amenity/category filters, sorting and favourites
hotel-detail.html   Selected hotel, gallery, amenities, weather and booking link
booking.html        Three steps: stay, guest details, review and confirmation
services.html       Travel services and a dynamic price estimator
about.html          Project purpose, original team and local contact draft form
signup.html         Local demo registration with JavaScript validation
login.html          Local credential check and redirect to profile
profile.html        Account details, saved stays, bookings and cancellation

HOW TO DEMONSTRATE
1. On Home, choose Miami and any future check-in/check-out dates, then 2 guests.
2. Search results update instantly with text, category and amenity filters.
   Try 'pool', 'Astana', 'Paris' or an unmatched word; Clear filters resets them.
   Sorting and filters persist. The heart buttons save favourites.
3. Open Ocean View Resort. The selected stay and dates reach the booking page.
   Open-Meteo shows current weather plus three days, with loading/error/retry.
4. Choose Deluxe and Car rental. For 3 nights: ($220+$40)*3 + $55*3 = $945.
5. Invalid/empty inputs show errors below fields. Continue to Review.
6. Create a demo account using invented details. A password such as Travel2026!
   demonstrates uppercase, lowercase, digit and symbol checks. Do not reuse a
   real password. Registration/login opens Profile. Continue booking returns
   to the chosen trip with the entered information preserved.
7. Confirm the demo acknowledgement and save. The profile shows the booking.
   Cancel requires an explicit inline confirmation; keeping it is also possible.
8. Toggle the sun/moon button, change page and reload. The appearance persists.
9. In Services, compare transfer ($35 once), car ($55/day), tour ($45/person).
   Continue to booking keeps the selected service. Final cost uses trip dates
   and guests, as explained beside the estimator.
10. Contact saves a local draft, validates the selected reply method and can
    download a TXT copy. Newsletter also saves locally; neither sends email.

STORAGE AND AUTHENTICATION
All state uses localStorage with the bookingapp. prefix. Users are separate
records; the current session stores only userId. Passwords are stored as salted
SHA-256 digests rather than readable passwords. Authentication is a coursework
simulation, not a secure production identity system. Browser storage can be
inspected or changed by its owner and is not synchronized to other devices.
Keys include users, session, theme, search, filters, favorites.<userId>, bookings,
bookingDraft, pendingBookingUrl, contactDraft and newsletter.
Clearing this site's browser storage removes all locally saved information.

JAVASCRIPT VALIDATION
All forms use novalidate. Application code checks required values, email syntax,
password length/complexity, matching confirmation, international phone format,
future dates, date order, integer guest counts and service quantities.
No required, pattern, minlength, maxlength, min, max or type=email attributes
are used as the validation mechanism. Errors appear beside fields; focus moves
to the first invalid field. Authentication and storage errors remain visible.

API
Open-Meteo Forecast API: https://open-meteo.com/en/docs
GET https://api.open-meteo.com/v1/forecast
Uses each hotel's coordinates with current temperature/weather code and three
calendar days of weather code/min/max temperature. Requests use fetch and
async/await, a 12-second AbortController timeout, HTTP/response checks, a loading
state and retry UI. Attribution links to Open-Meteo. The forecast is current,
not the weather on the selected booking dates. No API key is shipped.

FILE ORGANIZATION
css/site.css             Shared tokens, page components, responsive/dark modes
js/theme-init.js         Appearance applied before first paint
js/common.js             Shared helpers, storage, validation, nav, notifications
js/hotels.js             Six illustrative listings and selected-hotel lookup
js/script.js             Home and dynamic search/filter behaviour
js/auth.js               Registration, login, profile, saved stays, cancellation
js/booking.js            Hotel details, trip continuity, booking and pricing
js/weather.js            Open-Meteo request and loading/error/success states
js/about-services.js     Contact drafts and service estimator
image/                   Existing local team/travel photos and SVG favicon
archive/                 Previous assignment reports and explanation (historical)

DESIGN AND ACCESSIBILITY
The approved Assignment 6-inspired design is applied to all nine pages: dark
navigation and footer, a cool grey background, white cards and blue actions.
Home uses the original beach/mountains/city triptych and a full-width search.
Search results, hotel details, booking, services, team, accounts and profile
share the same card, form and typography rules. Arial is used throughout.
CSS Grid and Flexbox provide responsive layouts. Light/dark modes persist in
localStorage. Forms retain JavaScript validation, labelled controls, inline
errors, visible keyboard focus and aria-live feedback. Navigation supports
Escape, and transitions respect reduced motion. The mobile newsletter form
stacks its email field and button without overlap. Essential comments remain.
The original approved sample is retained separately in design-preview/.
No third-party UI framework, external font, tracking script or backend is needed.

VERIFICATION
After the design migration, eleven browser regression groups passed with no
uncaught JavaScript errors. Tests covered signup/login/logout/profile, password
and field validation, search/filter/sort, favourites and guest-to-account
migration, full booking/review/confirmation/cancellation, all service estimates,
contact draft persistence/download/clear, newsletter, theme persistence and
mobile navigation. Live Open-Meteo weather and forced failure/retry also passed.
Grand Palace, Deluxe room, three nights and car rental totals $645.
All nine pages were checked at 320, 390, 768 and 1440 CSS pixels in both themes
for horizontal overflow, broken images and collapsed controls; none were found.
The newsletter was also checked at 360 and 600px for overlapping controls.
Measured field-border contrast: 3.13:1 light and 4.86:1 dark; primary-button text:
5.54:1 light and 8.12:1 dark. Test accounts exist only in isolated test browsers.
These checks cover the local build; publishing still requires updating hosting.

HOSTING
Repository: https://github.com/jjestar/final-web-frontend
Production website: https://aishhko-final.vercel.app
The current repository lists Vercel as its website; GitHub Pages is not enabled.
The entry point is index.html. The project is static and needs no build step.
Push completed changes to main, then verify that the Vercel production deployment
has updated successfully before sharing the website for assessment.

TEAM
The original project records these roles:
Allazhar Aldongarov — Frontend Developer
Dias Serikov — UI Designer
Yerkenov Abylay — Content and Testing
The report describes final features as shared project work, without assigning
unverified individual authorship of later changes.

SUBMISSION
Each student submits the complete project ZIP, the final PDF report and the TXT
with both links in Moodle FINAL EXAM FOLDER. Presentation: up to 5 minutes;
every team member participates. Deadline: 18 November 2026, 23:59.
