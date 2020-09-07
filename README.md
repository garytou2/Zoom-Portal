# Zoom Portal

Launch your Zoom participants in your zoom room using your custom domain.

## Firebase Realtime Database rules

```JSON
{
	"rules": {
		".read": false,
		".write": false,
		"home": {
			".read": true,
			".write": false,
			"joins": {
				".read": true,
				".write": false,
				"$meetingPushKey": {
					".read": true,
					".write": "!data.exists()",
					"$joinPushKey": {
						".read": true,
						".write": "!data.exists()"
					}
				}
			}
		},
		"openMeetings": {
			".read": true,
			".write": false,
			"joins": {
				".read": true,
				".write": false,
				"$meetingPushKey": {
					".read": true,
					".write": "!data.exists()",
					"$joinPushKey": {
						".read": true,
						".write": "!data.exists()"
					}
				}
			}
		}
	}
}

```
