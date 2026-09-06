Vehicle Service Management — Pega Application

Submitted by: Krupavaram Pamula (B.Tech CSE-AIML, Mohan Babu University, Andhra Pradesh)
Platform: Pega (instance: ce7ja0rw.pegaacademy.net)
Application name: NIP-VEHICLE SERVICE-KRUPAVARAM PAMULA
Case type: Vehicle Service Request

What it does

A case-management app that walks a vehicle through the full service lifecycle — from a customer submitting an issue to the vehicle being repaired and the customer notified.

Case flow: Request Intake → Inspection → Approval (with a reject branch) → Service Execution → Resolution

Key features (10 user stories)
Submit Vehicle Service Request – customer enters Vehicle ID, Model, and Issue Description with validation.
Vehicle Inspection – Service Advisor logs inspection notes and a condition rating.
Service Estimate – Labor Cost + Parts Cost entered; Total Cost auto-calculated via a Declare Expression.
Approve Service Estimate – customer approves/rejects, branching the flow accordingly.
Vehicle data object – reusable object storing Vehicle ID, Model, Type, Registration Number.
Review Service Estimate – itemized cost summary shown to the customer.
Auto-assign Technician – routes work to HeavyVehicleQueue or LightVehicleQueue based on vehicle type.
Notify Service Completion – correspondence/email triggered on resolution.
Service SLA – goal 2 days / deadline 3 days on the case type.
(10th story continues into SLA escalation, cut off in the excerpt I pulled — let me know if you want the exact wording.)
Notable design decisions
Declare Expression for Total Cost — recalculates automatically whenever Labor/Parts costs change, avoiding manual errors.
Business logic routing by vehicle type — heavy vs. light vehicles need different bays/skills, so cases route to the correct work queue automatically.
Personas

Customer, Service Advisor, Technician

Work queues
HeavyVehicleQueue — case property = Heavy
LightVehicleQueue — default/otherwise queue
