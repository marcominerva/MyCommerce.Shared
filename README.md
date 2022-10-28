# MyCommerce.Shared

This repository shows how to create and mantain a versioned library that must be shared across multiple repositories (i.e., in client/server or microservices scenarios):

- The library is published on GitHub NuGet registry.
- Every project that uses this library needs the following NuGet.config file:

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>
        <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
        <add key="github" value="https://nuget.pkg.github.com/OWNER/index.json" />
    </packageSources>
    <packageSourceCredentials>
        <github>
            <add key="Username" value="OWNER" />
            <add key="ClearTextPassword" value="TOKEN" />
        </github>
    </packageSourceCredentials>
</configuration>
```

More information are available at https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-nuget-registry.
