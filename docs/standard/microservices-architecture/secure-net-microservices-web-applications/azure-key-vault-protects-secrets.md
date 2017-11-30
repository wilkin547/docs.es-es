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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="8baa6-104">Con el almacén de claves de Azure para proteger información confidencial en tiempo de producción</span><span class="sxs-lookup"><span data-stu-id="8baa6-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="8baa6-105">Secretos almacenadas como variables de entorno o por la herramienta Administrador de secreto todavía se almacenan localmente y sin cifrar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8baa6-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="8baa6-106">Es una opción más segura para almacenar secretos [el almacén de claves de Azure](https://azure.microsoft.com/services/key-vault/), lo que proporciona una ubicación central y segura para almacenar claves y secretos.</span><span class="sxs-lookup"><span data-stu-id="8baa6-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="8baa6-107">El paquete Microsoft.Extensions.Configuration.AzureKeyVault permite que una aplicación de ASP.NET Core leer información de configuración de almacén de claves de Azure.</span><span class="sxs-lookup"><span data-stu-id="8baa6-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="8baa6-108">Para empezar a usar secretos de un almacén de claves de Azure, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8baa6-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="8baa6-109">En primer lugar, registrar la aplicación como una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8baa6-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="8baa6-110">(Acceso a almacenes de claves se administra mediante Azure AD). Esto puede hacerse a través del portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="8baa6-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="8baa6-111">O bien, si desea que la aplicación se autentiquen mediante un certificado en lugar de un secreto de cliente o la contraseña, puede usar el [AzureRmADApplication New](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8baa6-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="8baa6-112">El certificado que registre en el almacén de claves de Azure tiene solo su clave pública.</span><span class="sxs-lookup"><span data-stu-id="8baa6-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="8baa6-113">(La aplicación usará la clave privada).</span><span class="sxs-lookup"><span data-stu-id="8baa6-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="8baa6-114">En segundo lugar, proporcionan acceso a la aplicación registrada para el almacén de claves mediante la creación de una nueva entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="8baa6-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="8baa6-115">Puede hacerlo mediante los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8baa6-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="8baa6-116">En tercer lugar, incluya el almacén de claves como un origen de configuración de la aplicación llamando al método de extensión IConfigurationBuilder.AddAzureKeyVault cuando se crea una instancia de IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="8baa6-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="8baa6-117">Tenga en cuenta que al llamar a AddAzureKeyVault requerirán el identificador de aplicación que se ha registrado y concede acceso al almacén de claves en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8baa6-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="8baa6-118">Actualmente, el estándar de .NET y .NET Core admiten al obtener información de configuración de un almacén de claves de Azure mediante un identificador de cliente y el secreto del cliente.</span><span class="sxs-lookup"><span data-stu-id="8baa6-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="8baa6-119">Aplicaciones de .NET framework pueden utilizar una sobrecarga de IConfigurationBuilder.AddAzureKeyVault que toma un certificado en lugar del secreto del cliente.</span><span class="sxs-lookup"><span data-stu-id="8baa6-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="8baa6-120">Cuando se redactó este documento, un trabajo es [en curso](https://github.com/aspnet/Configuration/issues/605) para realizar esa sobrecarga disponible en el estándar de .NET y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8baa6-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="8baa6-121">Hasta que la sobrecarga de AddAzureKeyVault que acepta que un certificado está disponible, las aplicaciones de ASP.NET Core pueden tener acceso a un almacén de claves de Azure con la autenticación basada en certificados mediante la creación explícita de un objeto KeyVaultClient, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8baa6-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="8baa6-122">En este ejemplo, la llamada a AddAzureKeyVault se incluye al final del registro del proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="8baa6-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="8baa6-123">Es una práctica recomendada para registrar el almacén de claves de Azure como el último proveedor de configuración para que tenga una oportunidad para reemplazar los valores de configuración de proveedores anteriores, de modo que no hay valores de configuración de otros orígenes reemplazan a las que desde el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="8baa6-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8baa6-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8baa6-124">Additional resources</span></span>

-   <span data-ttu-id="8baa6-125">**Con el almacén de claves de Azure para proteger los secretos de aplicación**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="8baa6-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="8baa6-126">**Ubicación de almacenamiento segura de secretos de aplicación durante el desarrollo**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="8baa6-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="8baa6-127">**Configurar la protección de datos**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="8baa6-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="8baa6-128">**Administración y la duración de la clave**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#datos protección predeterminada configuración*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="8baa6-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="8baa6-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="8baa6-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="8baa6-130">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="8baa6-130">GitHub repo.</span></span>
    [<span data-ttu-id="8baa6-131">*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="8baa6-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="8baa6-132">[Anterior] (para desarrolladores-aplicaciones-secretos-storage.md) [siguiente] (.. / takeaways.md de clave)</span><span class="sxs-lookup"><span data-stu-id="8baa6-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
