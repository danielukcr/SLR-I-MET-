




<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Metropolitan Police HUB – South London Response</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: #0b1a2b;
            color: #f5f5f5;
            margin: 0;
        }
        header {
            background: #001f3f;
            padding: 15px 20px;
            border-bottom: 2px solid #004b8d;
        }
        header h1 {
            margin: 0;
            font-size: 1.4rem;
        }
        header p {
            margin: 5px 0 0;
            font-size: 0.85rem;
            color: #cccccc;
        }
        main {
            padding: 20px;
        }
        .card {
            background: #10233a;
            border: 1px solid #24486f;
            border-radius: 6px;
            padding: 15px;
            margin-bottom: 20px;
        }
        .card h2 {
            margin-top: 0;
            font-size: 1.1rem;
        }
        label {
            display: block;
            margin: 8px 0 3px;
            font-size: 0.9rem;
        }
        input, textarea, select {
            width: 100%;
            padding: 6px 8px;
            border-radius: 4px;
            border: 1px solid #355a82;
            background: #0b1726;
            color: #f5f5f5;
            font-size: 0.9rem;
        }
        textarea {
            min-height: 80px;
            resize: vertical;
        }
        button {
            margin-top: 10px;
            padding: 8px 14px;
            border-radius: 4px;
            border: none;
            background: #0074d9;
            color: #fff;
            font-weight: 600;
            cursor: pointer;
            font-size: 0.9rem;
        }
        button:hover {
            background: #005fa8;
        }
        .row {
            display: flex;
            gap: 10px;
        }
        .row > div {
            flex: 1;
        }
        .small {
            font-size: 0.8rem;
            color: #bbbbbb;
        }
        .hidden {
            display: none;
        }
        .notepad {
            background: #fdf6e3;
            color: #333;
            border-radius: 6px;
            padding: 10px;
            border: 1px solid #d3c7a3;
        }
        .notepad textarea {
            background: transparent;
            border: none;
            color: #333;
            font-family: "Courier New", monospace;
            min-height: 150px;
        }
        .notepad textarea:focus {
            outline: none;
        }
        .login-status {
            font-size: 0.8rem;
            margin-top: 5px;
        }
        .success {
            color: #2ecc71;
        }
        .error {
            color: #ff4136;
        }
    </style>
</head>
<body>
<header>
    <h1>Metropolitan Police HUB – South London Response</h1>
    <p>This is an official South London response website and is NOT an official Metropolitan Police website.</p>
</header>

<main>
    <!-- DISCLAIMER GATE -->
    <section id="disclaimer-card" class="card">
        <h2>Disclaimer</h2>
        <p>
            This hub is for South London response operations and training purposes only. It is not an official
            Metropolitan Police Service website. Misuse or false reporting may result in removal from the department.
        </p>
        <p>Do you understand or do you not understand?</p>
        <button id="btn-understand">I understand</button>
        <button id="btn-not-understand">I do not understand</button>
    </section>

    <!-- LOGIN -->
    <section id="login-card" class="card hidden">
        <h2>Officer Login</h2>
        <p class="small">Enter your Discord user and collar number to access the HUB.</p>
        <label for="loginDiscordUser">Discord user</label>
        <input id="loginDiscordUser" type="text" placeholder="e.g. AVG#0001">

        <label for="loginCollar">Collar number</label>
        <input id="loginCollar" type="text" placeholder="e.g. SL123">

        <button id="btn-login">Login</button>
        <div id="loginStatus" class="login-status"></div>
    </section>

    <!-- HUB CONTENT (VISIBLE AFTER LOGIN) -->
    <section id="hub-content" class="hidden">
        <!-- BASIC PANELS (NO PASSWORD) -->
        <section class="card">
            <h2>Police Collision Report</h2>
            <p class="small">Lying on this will result in immediate removal from the department.</p>

            <div class="row">
                <div>
                    <label for="crDiscordUser">Discord user</label>
                    <input id="crDiscordUser" type="text">
                </div>
                <div>
                    <label for="crDiscordId">Discord ID</label>
                    <input id="crDiscordId" type="text">
                </div>
            </div>

            <div class="row">
                <div>
                    <label for="crFullName">Full name</label>
                    <input id="crFullName" type="text">
                </div>
                <div>
                    <label for="crCollar">Collar number</label>
                    <input id="crCollar" type="text">
                </div>
            </div>

            <div class="row">
                <div>
                    <label for="crOtherVehicle">Other vehicle</label>
                    <input id="crOtherVehicle" type="text">
                </div>
                <div>
                    <label for="crOtherVrnCollar">Other VRN/Collar</label>
                    <input id="crOtherVrnCollar" type="text">
                </div>
            </div>

            <label for="crExplain">Explain what happened</label>
            <textarea id="crExplain"></textarea>

            <button id="btn-send-collision">Send collision report</button>
            <div id="crStatus" class="small"></div>
        </section>

        <section class="card">
            <h2>Use of Force Report</h2>

            <div class="row">
                <div>
                    <label for="ufDiscordUser">Discord user</label>
                    <input id="ufDiscordUser" type="text">
                </div>
                <div>
                    <label for="ufDiscordId">Discord ID</label>
                    <input id="ufDiscordId" type="text">
                </div>
            </div>

            <div class="row">
                <div>
                    <label for="ufFullName">Full name</label>
                    <input id="ufFullName" type="text">
                </div>
                <div>
                    <label for="ufCollar">Collar number</label>
                    <input id="ufCollar" type="text">
                </div>
            </div>

            <label for="ufForceUsage">What usage of force did you use?</label>
            <input id="ufForceUsage" type="text" placeholder="e.g. TASER deployment, baton strike">

            <label for="ufItemUsed">What item did you use (if any)</label>
            <select id="ufItemUsed">
                <option value="">Select item</option>
                <option value="TASER">TASER</option>
                <option value="BATON">BATON</option>
                <option value="PAVA">PAVA</option>
                <option value="Fist">Fist</option>
            </select>

            <label for="ufExplain">Explain what happened and why you used force</label>
            <textarea id="ufExplain"></textarea>

            <button id="btn-send-force">Send use of force report</button>
            <div id="ufStatus" class="small"></div>
        </section>

        <section class="card">
            <h2>ANPR Marker</h2>

            <label for="anprOwner">Vehicle owner</label>
            <input id="anprOwner" type="text">

            <label for="anprVrn">VRN</label>
            <input id="anprVrn" type="text">

            <label for="anprReason">Reason</label>
            <textarea id="anprReason"></textarea>

            <label for="anprMarkers">Markers</label>
            <textarea id="anprMarkers" placeholder="e.g. Weapons, drugs, fail to stop"></textarea>

            <label for="anprIssuedBy">Issued by</label>
            <input id="anprIssuedBy" type="text">

            <button id="btn-send-anpr">Send ANPR marker</button>
            <div id="anprStatus" class="small"></div>
        </section>

        <!-- PASSWORD PROTECTED: CODE ZERO LOGGING -->
        <section class="card">
            <h2>Code Zero Logging (Password Protected)</h2>
            <p class="small">Password required.</p>

            <label for="czPassword">Password</label>
            <input id="czPassword" type="password">

            <div id="czProtected" class="hidden">
                <div class="row">
                    <div>
                        <label for="czOfficerName">Officer name</label>
                        <input id="czOfficerName" type="text">
                    </div>
                    <div>
                        <label for="czOfficerCollar">Officer collar</label>
                        <input id="czOfficerCollar" type="text">
                    </div>
                </div>

                <label for="czLocation">Location</label>
                <input id="czLocation" type="text">

                <label for="czIssue">Issue</label>
                <textarea id="czIssue"></textarea>

                <label for="czUnitsNeeded">Units needed</label>
                <textarea id="czUnitsNeeded"></textarea>

                <button id="btn-send-codezero">Send Code Zero log</button>
                <div id="czStatus" class="small"></div>
            </div>

            <button id="btn-check-cz-password">Unlock Code Zero</button>
            <div id="czPasswordStatus" class="small"></div>
        </section>

        <!-- POLICE NOTEPAD -->
        <section class="card">
            <h2>Police Notepad</h2>
            <p class="small">Use this as your working notes. Content stays in this browser only.</p>
            <div class="notepad">
                <textarea id="notepadArea" placeholder="Start typing your notes here..."></textarea>
            </div>
            <button id="btn-save-notepad">Save notepad locally</button>
            <div id="notepadStatus" class="small"></div>
        </section>
    </section>
</main>

<script>
    // DISCLAIMER
    const disclaimerCard = document.getElementById('disclaimer-card');
    const btnUnderstand = document.getElementById('btn-understand');
    const btnNotUnderstand = document.getElementById('btn-not-understand');
    const loginCard = document.getElementById('login-card');
    const hubContent = document.getElementById('hub-content');

    btnUnderstand.addEventListener('click', () => {
        disclaimerCard.classList.add('hidden');
        loginCard.classList.remove('hidden');
    });

    btnNotUnderstand.addEventListener('click', () => {
        window.location.href = 'https://www.google.com';
    });

    // LOGIN (simple front-end gate)
    const btnLogin = document.getElementById('btn-login');
    const loginDiscordUser = document.getElementById('loginDiscordUser');
    const loginCollar = document.getElementById('loginCollar');
    const loginStatus = document.getElementById('loginStatus');

    btnLogin.addEventListener('click', () => {
        const user = loginDiscordUser.value.trim();
        const collar = loginCollar.value.trim();

        if (!user || !collar) {
            loginStatus.textContent = 'Both Discord user and collar number are required.';
            loginStatus.className = 'login-status error';
            return;
        }

        loginStatus.textContent = `Logged in as ${user} (${collar}). Basic HUB unlocked.`;
        loginStatus.className = 'login-status success';
        loginCard.classList.add('hidden');
        hubContent.classList.remove('hidden');
    });

    // WEBHOOK URLs
    const WEBHOOK_COLLISION_FORCE = 'https://discord.com/api/webhooks/1520625298012504115/LvbzpI4X3ecEhNn2CAomT5vwUvzcXO2GzedcPC8ImogIysMZVIYUBGhd77lDuZGnlS0f';
    const WEBHOOK_ANPR = 'https://discord.com/api/webhooks/1520625615651471362/wK1OMY-mJKPPgt2QZ9ufx2CHmBgKg2mCl87d6KygpyIw1ipQech0wRA7usB_IuEJj1It';

    // Helper: send to Discord webhook
    async function sendToWebhook(url, contentObj) {
        const payload = {
            content: null,
            embeds: [
                {
                    title: contentObj.title || 'Met HUB Submission',
                    description: contentObj.description || '',
                    color: 3447003,
                    fields: contentObj.fields || []
                }
            ]
        };

        const res = await fetch(url, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(payload)
        });

        if (!res.ok) {
            throw new Error('Webhook error: ' + res.status);
        }
    }

    // COLLISION REPORT
    const btnSendCollision = document.getElementById('btn-send-collision');
    const crStatus = document.getElementById('crStatus');

    btnSendCollision.addEventListener('click', async () => {
        const discordUser = document.getElementById('crDiscordUser').value.trim();
        const discordId = document.getElementById('crDiscordId').value.trim();
        const fullName = document.getElementById('crFullName').value.trim();
        const collar = document.getElementById('crCollar').value.trim();
        const otherVehicle = document.getElementById('crOtherVehicle').value.trim();
        const otherVrnCollar = document.getElementById('crOtherVrnCollar').value.trim();
        const explain = document.getElementById('crExplain').value.trim();

        if (!discordUser || !discordId || !fullName || !collar || !explain) {
            crStatus.textContent = 'Required fields missing. Please complete all main fields.';
            crStatus.className = 'small error';
            return;
        }

        crStatus.textContent = 'Sending collision report...';
        crStatus.className = 'small';

        try {
            await sendToWebhook(WEBHOOK_COLLISION_FORCE, {
                title: 'Police Collision Report',
                description: 'New collision report submitted via Met HUB.',
                fields: [
                    { name: 'Discord user', value: discordUser, inline: true },
                    { name: 'Discord ID', value: discordId, inline: true },
                    { name: 'Full name', value: fullName, inline: true },
                    { name: 'Collar number', value: collar, inline: true },
                    { name: 'Other vehicle', value: otherVehicle || 'N/A', inline: true },
                    { name: 'Other VRN/Collar', value: otherVrnCollar || 'N/A', inline: true },
                    { name: 'Explanation', value: explain || 'N/A', inline: false }
                ]
            });
            crStatus.textContent = 'Collision report sent to Discord.';
            crStatus.className = 'small success';
        } catch (e) {
            crStatus.textContent = 'Failed to send collision report.';
            crStatus.className = 'small error';
        }
    });

    // USE OF FORCE REPORT
    const btnSendForce = document.getElementById('btn-send-force');
    const ufStatus = document.getElementById('ufStatus');

    btnSendForce.addEventListener('click', async () => {
        const discordUser = document.getElementById('ufDiscordUser').value.trim();
        const discordId = document.getElementById('ufDiscordId').value.trim();
        const fullName = document.getElementById('ufFullName').value.trim();
        const collar = document.getElementById('ufCollar').value.trim();
        const forceUsage = document.getElementById('ufForceUsage').value.trim();
        const itemUsed = document.getElementById('ufItemUsed').value;
        const explain = document.getElementById('ufExplain').value.trim();

        if (!discordUser || !discordId || !fullName || !collar || !forceUsage || !explain) {
            ufStatus.textContent = 'Required fields missing. Please complete all main fields.';
            ufStatus.className = 'small error';
            return;
        }

        ufStatus.textContent = 'Sending use of force report...';
        ufStatus.className = 'small';

        try {
            await sendToWebhook(WEBHOOK_COLLISION_FORCE, {
                title: 'Use of Force Report',
                description: 'New use of force report submitted via Met HUB.',
                fields: [
                    { name: 'Discord user', value: discordUser, inline: true },
                    { name: 'Discord ID', value: discordId, inline: true },
                    { name: 'Full name', value: fullName, inline: true },
                    { name: 'Collar number', value: collar, inline: true },
                    { name: 'Usage of force', value: forceUsage, inline: false },
                    { name: 'Item used', value: itemUsed || 'Not specified', inline: true },
                    { name: 'Explanation', value: explain, inline: false }
                ]
            });
            ufStatus.textContent = 'Use of force report sent to Discord.';
            ufStatus.className = 'small success';
        } catch (e) {
            ufStatus.textContent = 'Failed to send use of force report.';
            ufStatus.className = 'small error';
        }
    });

    // CODE ZERO (PASSWORD PROTECTED)
    const btnCheckCzPassword = document.getElementById('btn-check-cz-password');
    const czPasswordInput = document.getElementById('czPassword');
    const czProtected = document.getElementById('czProtected');
    const czPasswordStatus = document.getElementById('czPasswordStatus');
    const btnSendCodeZero = document.getElementById('btn-send-codezero');
    const czStatus = document.getElementById('czStatus');

    const CODE_ZERO_PASSWORD = '403043040_SLR_2030302030';

    btnCheckCzPassword.addEventListener('click', () => {
        const entered = czPasswordInput.value;
        if (entered === CODE_ZERO_PASSWORD) {
            czProtected.classList.remove('hidden');
            czPasswordStatus.textContent = 'Password accepted. Code Zero logging unlocked.';
            czPasswordStatus.className = 'small success';
        } else {
            czProtected.classList.add('hidden');
            czPasswordStatus.textContent = 'Incorrect password.';
            czPasswordStatus.className = 'small error';
        }
    });

    btnSendCodeZero.addEventListener('click', async () => {
        const officerName = document.getElementById('czOfficerName').value.trim();
        const officerCollar = document.getElementById('czOfficerCollar').value.trim();
        const location = document.getElementById('czLocation').value.trim();
        const issue = document.getElementById('czIssue').value.trim();
        const unitsNeeded = document.getElementById('czUnitsNeeded').value.trim();

        if (!officerName || !officerCollar || !location || !issue) {
            czStatus.textContent = 'Required fields missing. Please complete all main fields.';
            czStatus.className = 'small error';
            return;
        }

        czStatus.textContent = 'Sending Code Zero log...';
        czStatus.className = 'small';

        try {
            await sendToWebhook(WEBHOOK_COLLISION_FORCE, {
                title: 'Code Zero Log',
                description: 'Code Zero declared via Met HUB.',
                fields: [
                    { name: 'Officer name', value: officerName, inline: true },
                    { name: 'Officer collar', value: officerCollar, inline: true },
                    { name: 'Location', value: location, inline: false },
                    { name: 'Issue', value: issue, inline: false },
                    { name: 'Units needed', value: unitsNeeded || 'Not specified', inline: false }
                ]
            });
            czStatus.textContent = 'Code Zero log sent to Discord.';
            czStatus.className = 'small success';
        } catch (e) {
            czStatus.textContent = 'Failed to send Code Zero log.';
            czStatus.className = 'small error';
        }
    });

    // ANPR MARKER
    const btnSendAnpr = document.getElementById('btn-send-anpr');
    const anprStatus = document.getElementById('anprStatus');

    btnSendAnpr.addEventListener('click', async () => {
        const owner = document.getElementById('anprOwner').value.trim();
        const vrn = document.getElementById('anprVrn').value.trim();
        const reason = document.getElementById('anprReason').value.trim();
        const markers = document.getElementById('anprMarkers').value.trim();
        const issuedBy = document.getElementById('anprIssuedBy').value.trim();

        if (!owner || !vrn || !reason || !issuedBy) {
            anprStatus.textContent = 'Required fields missing. Please complete all main fields.';
            anprStatus.className = 'small error';
            return;
        }

        anprStatus.textContent = 'Sending ANPR marker...';
        anprStatus.className = 'small';

        try {
            await sendToWebhook(WEBHOOK_ANPR, {
                title: 'ANPR Marker',
                description: 'New ANPR marker submitted via Met HUB.',
                fields: [
                    { name: 'Vehicle owner', value: owner, inline: true },
                    { name: 'VRN', value: vrn, inline: true },
                    { name: 'Reason', value: reason, inline: false },
                    { name: 'Markers', value: markers || 'None specified', inline: false },
                    { name: 'Issued by', value: issuedBy, inline: true }
                ]
            });
            anprStatus.textContent = 'ANPR marker sent to Discord.';
            anprStatus.className = 'small success';
        } catch (e) {
            anprStatus.textContent = 'Failed to send ANPR marker.';
            anprStatus.className = 'small error';
        }
    });

    // POLICE NOTEPAD (LOCAL STORAGE)
    const notepadArea = document.getElementById('notepadArea');
    const btnSaveNotepad = document.getElementById('btn-save-notepad');
    const notepadStatus = document.getElementById('notepadStatus');

    // Load existing notes
    const savedNotes = localStorage.getItem('metHubNotepad');
    if (savedNotes) {
        notepadArea.value = savedNotes;
        notepadStatus.textContent = 'Loaded saved notepad from this browser.';
        notepadStatus.className = 'small';
    }

    btnSaveNotepad.addEventListener('click', () => {
        localStorage.setItem('metHubNotepad', notepadArea.value);
        notepadStatus.textContent = 'Notepad saved locally in this browser.';
        notepadStatus.className = 'small success';
    });
</script>
</body>
</html>
