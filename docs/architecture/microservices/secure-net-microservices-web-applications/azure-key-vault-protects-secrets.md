---
title: Usar Azure Key Vault para proteger secretos en tiempo de producción
description: 'Seguridad en microservicios de .NET y aplicaciones web: Azure Key Vault es una forma excelente de gestionar secretos de aplicación controlados en su totalidad por administradores. Los administradores incluso pueden asignar y revocar valores de desarrollo sin necesidad de que los desarrolladores tengan que gestionarlos.'
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 4d121f584188c5d5fa9ddf0d91bea5e107eff0cb
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899658"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="45c6c-104">Usar Azure Key Vault para proteger secretos en tiempo de producción</span><span class="sxs-lookup"><span data-stu-id="45c6c-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="45c6c-105">Los secretos almacenados como variables de entorno o almacenados por la herramienta Administrador de secretos todavía se almacenan localmente y se descifran en el equipo.</span><span class="sxs-lookup"><span data-stu-id="45c6c-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="45c6c-106">Una opción más segura para almacenar secretos es [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), que proporciona una ubicación central y segura para almacenar claves y secretos.</span><span class="sxs-lookup"><span data-stu-id="45c6c-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="45c6c-107">El paquete **Microsoft.Extensions.Configuration.AzureKeyVault** permite que una aplicación de ASP.NET Core lea información de configuración de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="45c6c-107">The **Microsoft.Extensions.Configuration.AzureKeyVault** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="45c6c-108">Siga estos pasos para empezar a usar secretos de Azure Key Vault:</span><span class="sxs-lookup"><span data-stu-id="45c6c-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="45c6c-109">Registre la aplicación como una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45c6c-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="45c6c-110">(el acceso a los almacenes de claves se administra mediante Azure AD). Puede hacerlo a través del portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="45c6c-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>\

   <span data-ttu-id="45c6c-111">Como alternativa, si quiere que la aplicación se autentique mediante un certificado en lugar de hacerlo con una contraseña o un secreto de cliente, puede usar el cmdlet de PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication).</span><span class="sxs-lookup"><span data-stu-id="45c6c-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="45c6c-112">El certificado que registre en Azure Key Vault solo necesita su clave pública</span><span class="sxs-lookup"><span data-stu-id="45c6c-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="45c6c-113">La aplicación usará la clave privada.</span><span class="sxs-lookup"><span data-stu-id="45c6c-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="45c6c-114">Conceda a la aplicación registrada acceso al almacén de claves creando una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="45c6c-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="45c6c-115">Puede hacerlo usando los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="45c6c-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="45c6c-116">Incluya el almacén de claves como origen de configuración en la aplicación llamando al método de extensión <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> cuando cree una instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.</span><span class="sxs-lookup"><span data-stu-id="45c6c-116">Include the key vault as a configuration source in your application by calling the <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span> <span data-ttu-id="45c6c-117">Tenga en cuenta que, al llamar a `AddAzureKeyVault` necesitará el Id. de la aplicación registrada y a la que se concedió acceso al almacén de claves en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="45c6c-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span>

   <span data-ttu-id="45c6c-118">También puede usar una sobrecarga de `AddAzureKeyVault` que toma un certificado en lugar del secreto de cliente solo incluyendo una referencia al paquete [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory).</span><span class="sxs-lookup"><span data-stu-id="45c6c-118">You can also use an overload of `AddAzureKeyVault` that takes a certificate in place of the client secret by just including a reference to the [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45c6c-119">Le recomendamos que registre Azure Key Vault como el último proveedor de configuración para que pueda invalidar los valores de configuración de proveedores anteriores.</span><span class="sxs-lookup"><span data-stu-id="45c6c-119">We recommend you to register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45c6c-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="45c6c-120">Additional resources</span></span>

- <span data-ttu-id="45c6c-121">**Using Azure Key Vault to protect application secrets (Usar Azure Key Vault para proteger secretos de aplicaciones)**  </span><span class="sxs-lookup"><span data-stu-id="45c6c-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault](/azure/guidance/guidance-multitenant-identity-keyvault)

- <span data-ttu-id="45c6c-122">**Safe storage of app secrets during development (Almacenamiento seguro de secretos de aplicación durante el desarrollo)**  </span><span class="sxs-lookup"><span data-stu-id="45c6c-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="45c6c-123">**Configuring data protection (Configuración de la protección de datos)**  </span><span class="sxs-lookup"><span data-stu-id="45c6c-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="45c6c-124">**Administración y duración de las claves de protección de datos en ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="45c6c-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="45c6c-125">Repositorio de GitHub **Microsoft.Extensions.Configuration.KeyPerFile**.</span><span class="sxs-lookup"><span data-stu-id="45c6c-125">**Microsoft.Extensions.Configuration.KeyPerFile** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration/Config.KeyPerFile>

>[!div class="step-by-step"]
><span data-ttu-id="45c6c-126">[Anterior](developer-app-secrets-storage.md)
>[Siguiente](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="45c6c-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
