---
title: Usar Azure Key Vault para proteger secretos en tiempo de producción
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Usar Azure Key Vault para proteger secretos en tiempo de producción
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 171d9120e4817065ddafc9dfa9caa362694ddeb3
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105289"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="7a7b7-103">Usar Azure Key Vault para proteger secretos en tiempo de producción</span><span class="sxs-lookup"><span data-stu-id="7a7b7-103">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="7a7b7-104">Los secretos almacenados como variables de entorno o almacenados por la herramienta Administrador de secretos todavía se almacenan localmente y se descifran en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-104">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="7a7b7-105">Una opción más segura para almacenar secretos es [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), que proporciona una ubicación central y segura para almacenar claves y secretos.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-105">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="7a7b7-106">El paquete Microsoft.Extensions.Configuration.AzureKeyVault permite que una aplicación de ASP.NET Core lea información de configuración de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-106">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="7a7b7-107">Siga estos pasos para empezar a usar secretos de Azure Key Vault:</span><span class="sxs-lookup"><span data-stu-id="7a7b7-107">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="7a7b7-108">En primer lugar, registre la aplicación como una aplicación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a7b7-108">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="7a7b7-109">(el acceso a los almacenes de claves se administra mediante Azure AD). Puede hacerlo a través del portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-109">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="7a7b7-110">Como alternativa, si quiere que la aplicación se autentique mediante un certificado en lugar de hacerlo con una contraseña o un secreto de cliente, puede usar el cmdlet de PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication).</span><span class="sxs-lookup"><span data-stu-id="7a7b7-110">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="7a7b7-111">El certificado que registre en Azure Key Vault solo necesita su clave pública</span><span class="sxs-lookup"><span data-stu-id="7a7b7-111">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="7a7b7-112">(la aplicación usará la clave privada).</span><span class="sxs-lookup"><span data-stu-id="7a7b7-112">(Your application will use the private key.)</span></span>

<span data-ttu-id="7a7b7-113">En segundo lugar, conceda a la aplicación registrada acceso al almacén de claves creando una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-113">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="7a7b7-114">Puede hacerlo usando los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7a7b7-114">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="7a7b7-115">En tercer lugar, incluya el almacén de claves como origen de configuración en la aplicación llamando al método de extensión IConfigurationBuilder.AddAzureKeyVault cuando cree una instancia de IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-115">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="7a7b7-116">Tenga en cuenta que, al llamar a AddAzureKeyVault, necesitará el Id. de la aplicación registrada y a la que se concedió acceso al almacén de claves en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-116">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="7a7b7-117">Actualmente, .NET Standard y .NET Core admiten la obtención de información de configuración de Azure Key Vault mediante un identificador de cliente y un secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-117">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="7a7b7-118">Las aplicaciones de .NET Framework pueden usar una sobrecarga de IConfigurationBuilder.AddAzureKeyVault que toma un certificado en lugar del secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-118">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="7a7b7-119">En el momento en el que se redactó este documento, [se estaba trabajando](https://github.com/aspnet/Configuration/issues/605) para que esa sobrecarga estuviera disponible en .NET Standard y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-119">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="7a7b7-120">Mientras la sobrecarga de AddAzureKeyVault que acepta un certificado no está disponible, las aplicaciones de ASP.NET Core pueden obtener acceso a un Azure Key Vault con una autenticación basada en certificados creando de manera explícita un objeto KeyVaultClient, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a7b7-120">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="7a7b7-121">En este ejemplo, la llamada a AddAzureKeyVault se incluye al final del registro del proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-121">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="7a7b7-122">Como procedimiento recomendado puede registrar Azure Key Vault como el último proveedor de configuración para que pueda reemplazar los valores de configuración de los proveedores anteriores, de modo que ningún valor de configuración de otros orígenes reemplace los del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-122">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a7b7-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7a7b7-123">Additional resources</span></span>

-   <span data-ttu-id="7a7b7-124">**Using Azure Key Vault to protect application secrets (Usar Azure Key Vault para proteger secretos de aplicaciones)**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="7a7b7-124">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="7a7b7-125">**Safe storage of app secrets during development (Almacenamiento seguro de secretos de aplicación durante el desarrollo)**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="7a7b7-125">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="7a7b7-126">**Configuring data protection (Configuración de la protección de datos)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="7a7b7-126">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="7a7b7-127">**Key management and lifetime**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings) (Administración y duración de las claves)</span><span class="sxs-lookup"><span data-stu-id="7a7b7-127">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="7a7b7-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="7a7b7-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="7a7b7-129">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="7a7b7-129">GitHub repo.</span></span>
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="7a7b7-130">[Anterior](developer-app-secrets-storage.md)
[Siguiente](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="7a7b7-130">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
