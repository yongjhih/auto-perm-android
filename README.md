# auto-perm-android

Wrap all permissions needed Android APIs, and auto request permissions while these wrapped APIs calling.
And support exception handler and featured listeners.

## TODO

```java
auto.perm.android.CallLog.Calls.getLastOutgoing(context);

AutoPerm.exception(e -> {}); // all exceptions handler

AutoPerm.on(auto.perm.android.CallLog.Calls.getLastOutgoing(any(Context.class)).exception(e -> {
});

AutoPerm.on(auto.perm.android.CallLog.Calls.getLastOutgoing(any(Context.class)).granted(e -> {
});

AutoPerm.on(auto.perm.android.CallLog.Calls.getLastOutgoing(any(Context.class)).request(context -> {
});

AutoPerm.on(auto.perm.android.CallLog.Calls.getLastOutgoing(any(Context.class)).denied(context -> {
});


package auto.perm.android;

public class CallLog {
    public static class Calls {
        @AutoPerm(permissions = {
            Manifest.permission.READ_CONTACTS,
            Manifest.permission.CALL_PHONE})
        public static String getLastOutgoing(Context context) {
            android.provider.CallLog.Calls.getLastOutgoing(context);
        }

        // @AutoPerm(permissions = {
        //     Manifest.permission.READ_CONTACTS,
        //     Manifest.permission.CALL_PHONE},
        //     request = AutoPermAlertDialog.class, granted = AutoPermAlertDialog.class, denied = AutoPermAlertDialog.class)
}
```
