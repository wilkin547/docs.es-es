---
title: "Con el almacén de claves de Azure para proteger información confidencial en tiempo de producción"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Con el almacén de claves de Azure para proteger información confidencial en tiempo de producción"
keywords: Docker, microservicios, ASP.NET, contenedor
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Con el almacén de claves de Azure para proteger información confidencial en tiempo de producción

Secretos almacenadas como variables de entorno o por la herramienta Administrador de secreto todavía se almacenan localmente y sin cifrar en el equipo. Es una opción más segura para almacenar secretos [el almacén de claves de Azure](https://azure.microsoft.com/services/key-vault/), lo que proporciona una ubicación central y segura para almacenar claves y secretos.

El paquete Microsoft.Extensions.Configuration.AzureKeyVault permite que una aplicación de ASP.NET Core leer información de configuración de almacén de claves de Azure. Para empezar a usar secretos de un almacén de claves de Azure, siga estos pasos:

En primer lugar, registrar la aplicación como una aplicación de Azure AD. (Acceso a almacenes de claves se administra mediante Azure AD). Esto puede hacerse a través del portal de administración de Azure.

O bien, si desea que la aplicación se autentiquen mediante un certificado en lugar de un secreto de cliente o la contraseña, puede usar el [AzureRmADApplication New](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) cmdlet de PowerShell. El certificado que registre en el almacén de claves de Azure tiene solo su clave pública. (La aplicación usará la clave privada).

En segundo lugar, proporcionan acceso a la aplicación registrada para el almacén de claves mediante la creación de una nueva entidad de servicio. Puede hacerlo mediante los siguientes comandos de PowerShell:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

En tercer lugar, incluya el almacén de claves como un origen de configuración de la aplicación llamando al método de extensión IConfigurationBuilder.AddAzureKeyVault cuando se crea una instancia de IConfigurationRoot. Tenga en cuenta que al llamar a AddAzureKeyVault requerirán el identificador de aplicación que se ha registrado y concede acceso al almacén de claves en los pasos anteriores.

  Actualmente, el estándar de .NET y .NET Core admiten al obtener información de configuración de un almacén de claves de Azure mediante un identificador de cliente y el secreto del cliente. Aplicaciones de .NET framework pueden utilizar una sobrecarga de IConfigurationBuilder.AddAzureKeyVault que toma un certificado en lugar del secreto del cliente. Cuando se redactó este documento, un trabajo es [en curso](https://github.com/aspnet/Configuration/issues/605) para realizar esa sobrecarga disponible en el estándar de .NET y .NET Core. Hasta que la sobrecarga de AddAzureKeyVault que acepta que un certificado está disponible, las aplicaciones de ASP.NET Core pueden tener acceso a un almacén de claves de Azure con la autenticación basada en certificados mediante la creación explícita de un objeto KeyVaultClient, tal como se muestra en el ejemplo siguiente:

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

En este ejemplo, la llamada a AddAzureKeyVault se incluye al final del registro del proveedor de configuración. Es una práctica recomendada para registrar el almacén de claves de Azure como el último proveedor de configuración para que tenga una oportunidad para reemplazar los valores de configuración de proveedores anteriores, de modo que no hay valores de configuración de otros orígenes reemplazan a las que desde el almacén de claves.

## <a name="additional-resources"></a>Recursos adicionales

-   **Con el almacén de claves de Azure para proteger los secretos de aplicación**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Ubicación de almacenamiento segura de secretos de aplicación durante el desarrollo**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Configurar la protección de datos**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Administración y la duración de la clave**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#datos protección predeterminada configuración*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** Repositorio de GitHub.
    [*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Anterior] (para desarrolladores-aplicaciones-secretos-storage.md) [siguiente] (.. / takeaways.md de clave)
