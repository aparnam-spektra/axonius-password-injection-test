
# Password Injection Validation

<blockquote class="overview">
  This document validates different injection keys available in the CloudLabs environment to identify the appropriate key for displaying the generated admin password in the lab login guide.
</blockquote>

## 1. Existing Injection Key – TenantID

**Injection Key:**

<inject key="TenantID" enableCopy="true" style="color:#FF6112" />

**Observation:**

The injection successfully populates a value. However, the returned value is the Tenant ID, not the actual admin password.

<blockquote class="info">
  <strong>Result:</strong> The injection key is working, but it does not meet the password injection requirement.
</blockquote>

---

## 2. Customer-Reported Injection Key – Password

**Injection Key:**

<inject key="Password" enableCopy="true" style="color:#FF6112" />

**Observation:**

The injection key does not populate any value in the lab guide.

<blockquote class="warning">
  <strong>Result:</strong> No value is returned for the customer-reported Password injection key.
</blockquote>

---

## 3. Alternative Injection Key – AzureAdUserPassword

**Injection Key:**

<inject key="AzureAdUserPassword" enableCopy="true" style="color:#FF6112" />

**Observation:**

The injection successfully populates a password value. The copy functionality is also available.

<blockquote class="info">
  <strong>Result:</strong> The alternative injection key successfully populates a password value in the lab guide.
</blockquote>

---

## 4. Test Results Summary

| Injection Key | Test Result |
|---|---|
| TenantID | Tenant ID populated |
| Password | No value populated |
| AzureAdUserPassword | Password value populated |

---

## 5. Conclusion

Based on the testing performed in the Spektra Test/Fix environment:

- `TenantID` populates the tenant identifier.
- `Password` does not populate any value.
- `AzureAdUserPassword` successfully populates a password value.

<blockquote class="overview">
  <strong>Recommended Alternative:</strong> AzureAdUserPassword can be considered as an alternative injection key, subject to validation against the Axonius admin password-reset and login process.
</blockquote>

## 6. Next Steps

1. Validate the injected password on the Axonius password-reset page.
2. Verify that the same password can be used to log in.
3. Share the validated alternative with the concerned team.

</div>
