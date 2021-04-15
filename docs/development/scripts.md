# Scripts

In addition to regular commands, there are some scripts available which combine popular commands to achieve specific outcomes. These can be found in `./scripts` and are documentated below.

## Development

### Start

The start script starts the required services, removing any attached volumes and forcing a rebuild of the environments resulting in a fresh project build.

```
./scripts/control/start_development_server.sh
```

## Testing

### Unit Tests

A script to run the unit tests can be found at `./scripts/ci/test.sh`
```

### Integration Tests

A script to run the integration tests can be found at `./scripts/development/run-integration-backstop-tests.sh`
