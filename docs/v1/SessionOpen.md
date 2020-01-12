SessionOpen function
======

Creates a new session.

# Syntax

```C
typedef
_IRQL_requires_max_(PASSIVE_LEVEL)
QUIC_STATUS
(QUIC_API * QUIC_SESSION_OPEN_FN)(
    _In_ _Pre_defensive_ HQUIC Registration,
    _In_reads_z_(QUIC_MAX_ALPN_LENGTH)
        const char* Alpn,    // Application-Layer Protocol Negotiation
    _In_opt_ void* Context,
    _Outptr_ _At_(*Session, __drv_allocatesMem(Mem)) _Pre_defensive_
        HQUIC* Session
    );
```

# Parameters

`Registration`

The valid handle to an open registration object.

`Alpn`

A null-terminated string for the Application-Layer Protocol Negotiation (ALPN) TLS extension.

`Context`

The app context pointer to be associated with the session object.

`Connection`

On success, returns a handle to the newly opened session object.


# Return Value

The function returns a [QUIC_STATUS](../v0/QUIC_STATUS.md). The app may use `QUIC_FAILED` or `QUIC_SUCCEEDED` to determine if the function failed or succeeded.

# Remarks

**TODO**

# See Also

[SessionClose](SessionClose.md)<br>
[SessionShutdown](SessionShutdown.md)<br>