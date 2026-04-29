Hyde Park Equipment — Warranty Management System
A warranty claim management web app for Hyde Park Equipment Ltd. Built for HYD010 (London) and HYD020 locations. Manages the full warranty lifecycle from work order review through OEM submission, reconciliation, and archive.

Live App
https://adammason00.github.io/hpe-warranty/
Bookmark on phones and tablets — works as a mobile web app.

Current Version — v9
File: index.html (273KB, standalone, no dependencies)
Data source: warranty_data.csv (exported from DMS, loaded on login)
Hosting: GitHub Pages (static, free)
Architecture: Single HTML file, vanilla JS, no frameworks
What's in v9

Real CSV work order data loaded on login (exported from DMS)
WO prefix routing — WS* = HYD010, WM* = HYD020
Service Advisor role (Stew, Bryan) — view-only WOs at their location
Management access via PIN (triple-tap logo → enter PIN)
Real photo upload with camera capture on mobile
Mobile photo uploader — shareable #upload URL for techs
Reconciliation with DMS closed WO tracking — flags missing OEM claim numbers and admin notes
Analytics with parts/labour/hours breakdown and individual user drill-down
OEM-specific claim writing coach (Kubota, Toro, Walker, Stihl)
AI Three Cs narrative review before manager approval
Part retention tracking with printable disposal labels


Locations & Staff
CodeManagerTechniciansHYD010SteveJohn, Jared, Tyler, Ed, Al, Logan, Caden, AlexHYD020BillAndrew, Alex, Nate, Don
Service Advisors: Stew (HYD010), Bryan (HYD020)
Warranty Admin: Andy
Admin/Finance: Anne
Management: Brian Apfelbeck, Adam Mason, John Williams — triple-tap gear logo → enter PIN 4824

Role Access
RoleWhoWhat They SeeTechnicianSelect name → Sign InMy Claims (own only), Pending WOs, New Claim with photo uploadService AdvisorStew / BryanWOs at their location (view-only), Add NotesWarranty AdminAndyFull claim workflow, OEM submissions, Task List, WO Review, Validity Checks, ArchiveService ManagerSteve / BillDashboard, All Claims (own location), Approvals, Info Requests, AnalyticsAdmin/FinanceAnneReconciliation, Pending Payment claimsManagementPIN accessEverything across both locations, Staff management

Claim Workflow
DMS Work Order Created
  → Tech Claims WO & Uploads Photos
    → Submits Claim (Three Cs + AI Review)
      → Service Manager Approves
        → Warranty Admin Submits to OEM Portal
          → OEM Issues Credit
            → Finance Reconciles
              → Closed → Archive
Target: claim submitted within 14 days of work completion.

CSV Data
The app loads work order data from warranty_data.csv on login. This file is exported from your DMS.
To update the CSV data:

Export work orders from your DMS
Rename the export file to warranty_data.csv
Go to the GitHub repo → click on warranty_data.csv → click the pencil icon
Delete all content → paste the new CSV data → Commit changes
The app will load the new data on next login

CSV columns used:
ColumnIndexDescriptionDivision0Location prefix (backup)Customer Last/First/Ext1-3Customer nameDoc Number8Work order number (WS* or WM*)Status11O = Open, C/R = ClosedDate Opened14WO open dateDays Open15Age in daysDate Closed17WO close dateDays to Close18Cycle timeSold By21Service advisorParts Amount23Parts billingLabour Amount24Labour billingOther Amount25Other chargesTotal Amount26Total billingHours Reported36Reported hoursHours Billed37Billed hoursMake (Long)40Equipment makeModel (Long)42Equipment modelSerial43Serial numberWarranty Code55OEM warranty codeWarranty Name56OEM warranty name

Updating the App
When you receive an updated index.html:

Go to the GitHub repo
Click on index.html
Click the pencil icon (Edit)
Select All (Ctrl+A) → Delete → Paste new file contents
Commit changes — deploys automatically within 60 seconds


Reconciliation
Closed DMS work orders automatically appear in the Reconciliation tab. The system flags:

🔴 Missing OEM Claim # — Warranty Admin must enter the OEM portal claim number
🟡 No Admin Notes — Add claim status notes for audit trail

Each row has inline entry for OEM claim numbers and an Add Note button. Once both are filled, the WO moves to Reconciliation History.

Mobile Photo Upload
Techs can upload warranty photos directly from their phone:

Open the app → tap Upload Photos in the sidebar (or navigate to [app-url]#upload)
Enter the Work Order number
Tap each slot to take a photo with the phone camera
Hit Save Photos to Claim

Photos stage in the browser and auto-attach when the claim is submitted from any device in the same session.
Shareable link: Copy the #upload URL and text it to a tech — works on any phone without logging in.

Production Upgrade Path
This version runs entirely in the browser — all data resets on refresh. When you're ready to make data persistent:
ServicePurposeCostSupabaseDatabase (replaces in-memory data)Free tierGoogle Drive APIPhoto/file storageFree (uses existing Drive)DMS APILive WO sync (replaces CSV)Depends on DMS vendor
Estimated developer cost to wire up the backend: $300–600 on Upwork/Fiverr using this prototype as the full specification.

Support
Built by Claude (Anthropic). For changes or issues, return to the Claude conversation with the project files attached and describe what needs updating.
