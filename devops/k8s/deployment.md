🔹 1️⃣ RollingUpdate (Default)

Updates Pods gradually, without downtime.

Creates new Pods step by step

Deletes old Pods step by step

Controlled by maxSurge and maxUnavailable

Safest and most commonly used

✅ Used in almost all production systems

🔹 2️⃣ Recreate

Deletes all old Pods first, then creates new ones.

No overlap between old and new

Causes downtime

Very simple strategy

⚠ Used when:

Application cannot run multiple versions at same time

Stateful or incompatible upgrades