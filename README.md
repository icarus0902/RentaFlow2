# RentFlow — Phase 2 Backend Starter

This package contains an initial Laravel backend scaffold for RentFlow. It is **not a full Laravel installation** and has not been deployed to the user's Hostinger VPS.

## Approved decisions
- Android client planned with Flutter/Dart.
- Backend: Laravel/PHP.
- Database: MySQL or MariaDB on the user's Hostinger VPS.
- English default (`en`), Spanish (`es`) supported, additional locales possible.
- International currency codes are stored per transaction; amounts use integer minor units.
- Administrators and tenants use one app with server-enforced permissions.
- Each owner receives their own payments directly, subject to payment provider support.
- Do not migrate providers without the owner's explicit authorization.

## Included
- Initial database migrations for roles/permissions, properties/buildings/units, tenants/leases, charges/payments/allocations, and owner payment-provider account metadata.
- Initial Eloquent models.
- Authentication route outline using Laravel Sanctum.
- Property and unit API controllers with basic server-side scoping.
- Property policy and feature tests for registration, owner isolation, cross-property unit access, and property creation.
- Test-environment runbook and explicit migration safety warnings.
- Payment confirmation design and Phase 2 checklist.

## Before use
1. Create a fresh Laravel project using a currently supported Laravel release and compatible PHP version.
2. Install/configure Laravel Sanctum and run its published migrations.
3. Copy these files into the fresh project and resolve any existing file conflicts.
4. Review all migrations and policies. Add request validation and authorization tests for every resource.
5. Follow `docs/TESTING_AND_SETUP.md` and use a disposable test database first; never run unreviewed migrations against production.
6. Configure secrets in server environment variables; never commit real credentials.
7. Add CI, backups, staging, HTTPS, monitoring, and rollback steps before production deployment.

## Important limitations
- This is not a complete production-ready backend. It does not yet include all controllers, tenant portal APIs, billing scheduler, email/WhatsApp/push integrations, real payment gateway, production deployment, or exhaustive security tests.
- The payment provider is not selected. Provider onboarding, multi-merchant support, webhook verification, fees, currencies and settlement must be verified before enabling live payments.
- No connection has been made to the user's Hostinger VPS or GitHub repository. The Laravel feature tests are authored but cannot be executed until this scaffold is installed in a complete Laravel project with Composer dependencies and a disposable test database.
