## What is it
EuphoriaLikeRagdoll is a Unity MonoBehaviour that simulates a physics-driven ragdoll
with enhanced balance, adaptive muscle tension, impact response, and an automated get-up/recovery system.
It uses Rigidbody forces/torques and ConfigurableJoint drives to produce some cool standing, stumbling, falling, flailing, and recovery behaviors.

## Key Features
- Body references:
  - hips, chest, head (required)
  - optional limbs: thighs, shins, upper arms, forearms for improved standing and flailing realism
- Balance & stabilization:
  - upright torque to keep torso upright when standing
  - spine/chest stabilization and head stabilization options
  - center-of-mass balancing using foot positions
- Adaptive muscle tension:
  - joint drive springs/dampers adjusted by "muscleTension" and an adaptive multiplier
  - can increase stiffness when unstable or recovering
- Falling & impact handling:
  - detects significant impacts and applies stability damage and impulse to body parts
  - arm flailing when falling to simulate instinctive movement
  - protective forces to reduce head impact
- Recovery system:
  - multi-phase get-up routine (rolling, torso push, leg push)
  - recovery timers, velocity/angular thresholds, and adaptive joint stiffness during recovery
- Physics tuning:
  - drag settings for airborne vs grounded states
  - velocity clamping and damping to avoid explosive responses
  - many exposed parameters (uprightTorque, balanceForce, legStraightenForce, etc.) for easy tweaking
- Predictive and corrective behaviors:
  - momentum compensation and predictive foot placement to step toward balance
  - leg straightening and knee torque to assist standing

  ## Basic Usage
1. Attach the EuphoriaLikeRagdoll script to the character root GameObject.
2. Assign the hips, chest, head Rigidbody fields, and optionally leg and arm rigidbodies in the Inspector.
3. Tune parameters in the Inspector to match mass, scale, and desired stiffness/realism.
4. Ensure ConfigurableJoints are set up on body parts so the script can modify joint drives.
