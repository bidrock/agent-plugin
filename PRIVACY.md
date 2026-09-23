# Integration data handling

Connecting an agent grants only the approved permissions in one Bidrock workspace. Bidrock rechecks membership, subscription and object access whenever the integration runs. Disconnecting prevents further access; it cannot remove copies already delivered to your chosen agent provider.

Your client receives the results you request, including relevant procurement information, workspace records, document excerpts/files and assistant responses. `openid` identifies your account; `email` additionally shares your verified email when approved. Your Bidrock password and browser session are not given to the external agent. The provider's own data handling applies to information it receives.

Bidrock stores the application, user, workspace, scopes, revocation and activity records. OAuth bearer tokens are represented by hashed lookup keys. Temporary transfer capabilities and mutation receipts are stored for retry protection. Assistant questions, answers and conversations use the existing Bidrock conversation storage. Operational audits record operation names, outcomes and times, rather than tool arguments or document contents.

Usage accounting is retained for 90 days and integration audit events for 365 days by the cleanup worker. Expiring protocol records are removed after their expiry; persistent connection records remain available for account history. Existing workspace records and assistant conversations follow the normal Bidrock policy. Cleanup is bounded and may lag during worker outages. Revocation is immediate on subsequent authorization checks and does not wait for cleanup.

See the [Bidrock privacy policy](https://bidrock.io/legal/privacy-policy). For access or deletion requests and integration support, contact [hello@bidrock.io](mailto:hello@bidrock.io). This note describes the implementation and does not replace the policy or customer agreement.
