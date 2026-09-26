# family-lab

Personal projects, research, and notes. Nothing here is production code — it's the
scratch space for things worth writing down.

## Vehicle projects

### 2007 Chevrolet Silverado 1500 Classic — 4.8L (Gen 3)

Suppressing check-engine-light codes caused by an aftermarket exhaust with no
downstream (post-catalyst) oxygen sensors.

- **Guide:** [`vehicle-projects/2007-silverado-classic-4-8l/silverado-classic-4-8l-o2-dtc-disable.html`](vehicle-projects/2007-silverado-classic-4-8l/silverado-classic-4-8l-o2-dtc-disable.html)
  — open it directly in a browser, no server needed

**Platform notes.** This is a GMT800 "Classic" with the 3rd-generation 4.8L
(LR4, VIN engine code `V`) — 24X crank reluctor, 1X cam gear, 3-bolt cam. Its
engine computer is in the GM P01/P59 family, *not* the E38 used in the GMT900
trucks of the same model year. That distinction matters: P01/P59 support segment
and clone writes in the open-source flashing tools, while E38 does not, and
existing community XDF definitions are available for P01/P59 but not E38.

**Approach.** Suppress the MIL for the specific downstream-sensor codes only,
leaving the recorded codes intact so every other warning light still functions.
Hardware is a single J2534 pass-through interface; the software is entirely free
and open source. Full write-up includes the segment/clone-write route, bench
flashing procedure, an alternative sensor-simulator option, and the failure modes
to watch for.

> **Status:** research compiled, not yet validated on the vehicle. Verify every
> address and definition before relying on them.
