# Standard Resolution Templates — Thrive Market IT Ops

These are the current resolution scripts used by L1 analysts. Each template includes the steps taken and the response sent to the requester.

---

## 1. Password Reset — Okta

**Trigger:** User locked out of Okta or requesting password reset.

**Resolution Steps:**
1. Verify identity: confirm employee ID and manager name
2. Initiate Okta password reset via admin console
3. Send temporary password via secure channel (Slack DM to verified account)
4. Set flag for mandatory password change on next login

**Response to User:**
> Your Okta password has been reset. You'll receive a temporary password via Slack DM. Please log in and set a new password immediately. If you don't receive the DM within 10 minutes, reply to this ticket.

**Avg Resolution Time:** 15 minutes

---

## 2. Password Reset — Google Workspace

**Trigger:** User locked out of Google Workspace or requesting password reset.

**Resolution Steps:**
1. Verify identity: confirm employee ID and manager name
2. Reset password via Google Admin Console
3. Send temporary password via Slack DM
4. Enforce password change on next login

**Response to User:**
> Your Google Workspace password has been reset. Check your Slack DMs for the temporary password. You'll be prompted to create a new one when you log in.

**Avg Resolution Time:** 15 minutes

---

## 3. New Application Access — Standard (Non-SOX)

**Trigger:** User requests access to a non-SOX application (Amplitude, Domo, Slack channels, Confluence).

**Resolution Steps:**
1. Verify the request matches the user's role in the system access matrix
2. Check with manager if role doesn't have standard access to the requested app
3. Provision access via Okta app assignment or direct admin console
4. Confirm access is working with the user

**Response to User:**
> Access to [application] has been provisioned to your Okta account. Log out and back in, then check your Okta dashboard. You should see [application] tile within 15 minutes. Let us know if you run into issues.

**Avg Resolution Time:** 30 minutes

---

## 4. New Application Access — SOX-Controlled

**Trigger:** User requests access to a SOX-controlled system (Snowflake write access, NetSuite, financial reporting tools).

**Resolution Steps:**
1. Verify request against system access matrix
2. Route to manager for approval (required — no auto-approve)
3. Route to system owner for secondary approval
4. Provision access after dual approval received
5. Log evidence of approval chain in Lumos

**Response to User:**
> Your access request for [system] requires manager and system owner approval (SOX compliance). We've routed the approvals — typical turnaround is 24-48 hours. You'll be notified once access is provisioned.

**Avg Resolution Time:** 36 hours (approval-dependent)

---

## 5. VPN Troubleshooting

**Trigger:** User unable to connect to VPN (GlobalProtect).

**Resolution Steps:**
1. Ask user to confirm: OS version, VPN client version, error message
2. Standard fixes: restart VPN client, clear cached credentials, re-authenticate via Okta
3. If persistent: check if user's device is compliant in Kandji (macOS) or Automox (Windows)
4. If device non-compliant: trigger compliance remediation and advise user to wait 15 min
5. Escalate to Network team if still unresolved

**Response to User:**
> Let's troubleshoot your VPN connection. Please try these steps in order: (1) Quit and reopen GlobalProtect, (2) Click "Sign Out" and re-authenticate with your Okta credentials, (3) If that doesn't work, restart your laptop and try again. If you're still stuck after all three, reply here and we'll dig deeper.

**Avg Resolution Time:** 45 minutes

---

## 6. New Laptop Setup — HQ / Remote

**Trigger:** New hire or replacement laptop request (macOS).

**Resolution Steps:**
1. Assign device from inventory in Kandji
2. Pre-configure MDM enrollment profile
3. Ship device (remote) or prepare for pickup (HQ)
4. Verify enrollment completion in Kandji within 48 hours
5. Confirm standard apps installed: Slack, Chrome, Zoom, Okta Verify, GlobalProtect

**Response to User:**
> Your new laptop is being prepared. [If HQ: It will be ready for pickup at the IT desk by end of day tomorrow.] [If remote: It will be shipped to your address on file — expect delivery in 3-5 business days.] Once you receive it, open the lid and follow the on-screen setup prompts. Everything will configure automatically via Kandji.

**Avg Resolution Time:** 24 hours (HQ) / 72 hours (remote, shipping)

---

## 7. Printer Setup — Fulfillment Center

**Trigger:** FC employee needs printer access or printer is down.

**Resolution Steps:**
1. Identify printer by FC location and zone (packing, shipping, receiving)
2. If access issue: add printer via print server, push config via Automox
3. If printer down: check printer status remotely, restart print spooler via Automox script
4. If hardware failure: create facilities ticket for physical repair

**Response to User:**
> [If access:] The printer for [zone] has been added to your workstation. Try printing a test page. [If down:] We've restarted the print service remotely. Give it 5 minutes and try again. If it's still not working, there may be a hardware issue and we'll send someone out.

**Avg Resolution Time:** 30 minutes (access) / 45 minutes (troubleshooting)

---

## 8. Pack-Station Reimaging — Fulfillment Center

**Trigger:** FC pack-station frozen, unresponsive, or needs reimaging after failed update.

**Resolution Steps:**
1. Identify station by FC location and station ID
2. Attempt remote restart via Automox
3. If unresponsive: trigger full reimage via Automox deployment script
4. Verify station comes back online and WMS client is functional
5. Notify FC shift lead when station is back

**Response to User:**
> We're reimaging pack-station [station ID] at [FC location] now. This typically takes 20-30 minutes. We'll notify your shift lead when it's back online. If you need to move to another station in the meantime, check with your lead for availability.

**Avg Resolution Time:** 35 minutes

---

## 9. Okta App Provisioning — Bulk (New Hire)

**Trigger:** New hire needs full app suite provisioned per their role.

**Resolution Steps:**
1. Pull role-based app list from system access matrix
2. Assign all standard apps via Okta group membership
3. Provision any apps requiring individual licenses (Zoom Pro, Figma, etc.)
4. Verify all apps appear in user's Okta dashboard
5. Send welcome message with app list and getting-started links

**Response to User:**
> Welcome to Thrive Market! Your accounts are set up. Log into Okta at thrive.okta.com with the credentials sent separately. You should see all your apps there: [list]. If anything's missing, reply to this ticket.

**Avg Resolution Time:** 45 minutes

---

## 10. Equipment Return — Offboarding

**Trigger:** Departing employee needs to return laptop and peripherals.

**Resolution Steps:**
1. Generate return shipping label (remote) or schedule HQ drop-off
2. Initiate remote lock via Kandji (macOS) or Automox (Windows) on last day
3. Verify device is returned and checked in to inventory
4. Wipe device after return confirmed
5. Update asset inventory

**Response to User:**
> [If remote:] A prepaid shipping label has been sent to your email. Please pack your laptop, charger, and any peripherals (monitor, keyboard, mouse) in the box they came in. Drop off at any UPS location within 5 business days. [If HQ:] Please drop off your equipment at the IT desk on your last day. We'll take care of the rest.

**Avg Resolution Time:** 20 minutes (initiation) / tracked until return
