<div align="center" style="text-align: center;">
  <img src="brave-mini-logo.svg" alt="Brave Mini logo" width="320" style="display: block; margin: 0 auto;">
</div>

# Brave Mini

A macOS configuration profile for a quieter Brave browser: fewer bundled extras, less reporting, and managed privacy defaults. It configures the existing browser; it is not a custom Brave build.

## What it does

The profile requests 28 mandatory preferences for `com.brave.Browser`:

- Disables Leo AI chat, Rewards, Wallet, Brave VPN, Tor windows, News, Talk, Playlist, Speedreader, and Wayback Machine integration.
- Disables P3A analytics, usage pings, Web Discovery contributions, and metrics reporting.
- Sets standard fingerprinting protection, ad blocking, and strict HTTPS upgrades. Enables De-AMP, debouncing, Global Privacy Control, reduced language exposure, and tracking-query filtering.
- Enables memory-saving settings and disables the built-in password manager, address/payment autofill, and translation.

Supported policies are enforced rather than offered as editable defaults. Strict HTTPS may show warnings on HTTP-only sites. Availability depends on your installed Brave version.

## What it does not do

- Does not install, patch, or update Brave, remove its bundled code, or guarantee better performance.
- Does not make browsing anonymous, block every tracker, or eliminate all network traffic and telemetry.
- Does not erase existing history, cookies, passwords, or wallet data.
- Does not configure extensions, Sync, search engines, or OS security, and does not target the separate Beta or Nightly preference domains.

## Use and verify

Review [the profile](brave-mini-config.mobileconfig) before installing it through macOS profile settings or your MDM. Installation is manual; recreating these files does not install or activate anything.

Restart Brave and open `brave://policy` to confirm which policies are recognized and applied. Unsupported entries may have no effect. Brave may display “Managed by your organization” because settings are enforced; this alone does not mean the device is remotely managed.

Remove the profile through macOS profile settings or your MDM to stop its enforcement. Other profiles or settings may still apply. The original profile identifiers and UUIDs are retained for continuity; the visible names now say Brave Mini.

## References

- [Brave policy administration](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy)
- [Fingerprinting policy values](https://github.com/brave/brave-core/blob/master/components/policy/resources/templates/policy_definitions/BraveSoftware/DefaultBraveFingerprintingV2Setting.yaml)
- [HTTPS upgrade policy values](https://github.com/brave/brave-core/blob/master/components/policy/resources/templates/policy_definitions/BraveSoftware/DefaultBraveHttpsUpgradeSetting.yaml)
- [Ad-blocking policy values](https://github.com/brave/brave-core/blob/master/components/policy/resources/templates/policy_definitions/BraveSoftware/DefaultBraveAdblockSetting.yaml)
