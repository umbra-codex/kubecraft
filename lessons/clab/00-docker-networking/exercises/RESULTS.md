# Lesson 0 — Docker Networking: Completion Notes

**Completed:** 2026-09-20
**Environment:** Arch Linux, Python 3.12.13, pytest 9.0.2

## Completion Checklist

- [x] Exercise 1: Inspected Docker's bridge, veth pairs, and container networking
- [x] Exercise 2: Built a namespace network from scratch with ping working
- [x] Exercise 3: Enabled NAT and reached the internet from a namespace
- [x] Exercise 4: Diagnosed and fixed a downed bridge
- [x] Exercise 5: Diagnosed and fixed a missing masquerade rule
- [x] Bonus: Docker Compose networking

## Test Results — 20/20 passed

```
$ uv run --project ../../.. --group test pytest tests/ -v

platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/umbra/Projects/kubecraft
configfile: pyproject.toml
collected 20 items

tests/test_docker_networking.py::TestDockerBasics::test_docker_available PASSED          [  5%]
tests/test_docker_networking.py::TestDockerBasics::test_docker_running PASSED            [ 10%]
tests/test_docker_networking.py::TestDefaultBridge::test_default_bridge_exists PASSED    [ 15%]
tests/test_docker_networking.py::TestDefaultBridge::test_default_bridge_subnet PASSED    [ 20%]
tests/test_docker_networking.py::TestDefaultBridge::test_docker0_interface_exists PASSED [ 25%]
tests/test_docker_networking.py::TestDefaultBridge::test_docker0_is_bridge PASSED        [ 30%]
tests/test_docker_networking.py::TestNamespaceLab::test_red_namespace_exists PASSED      [ 35%]
tests/test_docker_networking.py::TestNamespaceLab::test_blue_namespace_exists PASSED     [ 40%]
tests/test_docker_networking.py::TestNamespaceLab::test_bridge_exists PASSED             [ 45%]
tests/test_docker_networking.py::TestNamespaceLab::test_bridge_has_ip PASSED             [ 50%]
tests/test_docker_networking.py::TestNamespaceLab::test_veth_pairs_on_bridge PASSED      [ 55%]
tests/test_docker_networking.py::TestNamespaceLab::test_red_namespace_has_ip PASSED      [ 60%]
tests/test_docker_networking.py::TestNamespaceLab::test_blue_namespace_has_ip PASSED     [ 65%]
tests/test_docker_networking.py::TestNamespaceLab::test_red_can_ping_blue PASSED         [ 70%]
tests/test_docker_networking.py::TestNamespaceLab::test_blue_can_ping_red PASSED         [ 75%]
tests/test_docker_networking.py::TestNamespaceLab::test_namespace_can_ping_bridge PASSED [ 80%]
tests/test_docker_networking.py::TestNAT::test_ip_forwarding_enabled PASSED              [ 85%]
tests/test_docker_networking.py::TestNAT::test_forward_rules_exist PASSED                [ 90%]
tests/test_docker_networking.py::TestNAT::test_masquerade_rule_exists PASSED             [ 95%]
tests/test_docker_networking.py::TestNAT::test_namespace_has_default_route PASSED        [100%]
```
