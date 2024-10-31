# SIM, IMSI and MSISDN

In a mobile prepaid system, both the SIM card and the IMSI serve distinct roles, with the SIM acting as the physical resource and the IMSI as a key logical identifier:

1. **SIM (Subscriber Identity Module):** The SIM is the physical card inserted into a mobile device. It securely stores subscriber-related information, such as authentication keys, a unique identification number (ICCID), and other carrier-specific data. The SIM enables access to the mobile network by authenticating the user and allowing them to place calls, send messages, and use data.

2. **IMSI (International Mobile Subscriber Identity):** The IMSI is a logical identifier embedded within the SIM card. It is a unique, numeric code assigned to each subscriber by the mobile network operator. The IMSI is used by the network to identify and authenticate the subscriber on the network. While the IMSI is stored on the SIM, it is only transmitted to the network when necessary, with a temporary identifier (TMSI) often used to reduce the risk of interception.

In prepaid systems, the **SIM** enables network access, while the **IMSI** logically identifies the subscriber for authentication, billing, and usage tracking. The separation of these roles allows operators to manage and secure subscriber identity and activity effectively.

The **MSISDN (Mobile Station International Subscriber Directory Number)** is the phone number associated with the subscriber. While the IMSI is primarily used within the network for authentication and identification, the MSISDN is the public-facing number used for communication purposes (calls, SMS, data services) and billing.

Here's how it fits into the ecosystem:

1. **MSISDN as a Logical Resource**: The MSISDN is a logical resource linked to the subscriber account in the mobile operator’s database rather than being stored on the SIM. When a SIM card is assigned to a user, it is paired with an MSISDN to provide a unique contact number on the network.

2. **Separation from SIM and IMSI**: Unlike the SIM (physical) or IMSI (logical but hidden), the MSISDN is what other users use to reach the subscriber. It can also be reassigned independently of the SIM or IMSI. This flexibility allows operators to change the MSISDN if needed, such as when a user changes their number, without affecting the underlying SIM or IMSI.

3. **MSISDN and Prepaid Billing**: In prepaid systems, the MSISDN is crucial for tracking usage and managing prepaid balances. The mobile operator ties the balance and usage records to the MSISDN, allowing them to monitor call minutes, SMS, and data consumed by the subscriber.

To sum up:
- **SIM**: Physical card enabling network access.
- **IMSI**: Unique subscriber identifier on the network (logical, hidden).
- **MSISDN**: Public phone number (logical, user-facing) associated with billing and communication. 

Each component plays a distinct role in managing subscriber identity, network access, and service delivery.