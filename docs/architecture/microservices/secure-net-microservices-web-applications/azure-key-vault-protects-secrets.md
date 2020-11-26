---
title: Usar Azure Key Vault para proteger secretos en tiempo de producción
description: 'Seguridad en microservicios de .NET y aplicaciones web: Azure Key Vault es una forma excelente de gestionar secretos de aplicación controlados en su totalidad por administradores. Los administradores incluso pueden asignar y revocar valores de desarrollo sin necesidad de que los desarrolladores tengan que gestionarlos.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: d2d3690c0c8787ace6bcdfacbdb612f9ef957b98
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916247"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="68d1a-104">Usar Azure Key Vault para proteger secretos en tiempo de producción</span><span class="sxs-lookup"><span data-stu-id="68d1a-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="68d1a-105">Los secretos almacenados como variables de entorno o almacenados por la herramienta Administrador de secretos todavía se almacenan localmente y se descifran en el equipo.</span><span class="sxs-lookup"><span data-stu-id="68d1a-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="68d1a-106">Una opción más segura para almacenar secretos es [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), que proporciona una ubicación central y segura para almacenar claves y secretos.</span><span class="sxs-lookup"><span data-stu-id="68d1a-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="68d1a-107">El paquete **Azure.Extensions.AspNetCore.Configuration.Secrets** permite que una aplicación ASP.NET Core lea información de configuración de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="68d1a-107">The **Azure.Extensions.AspNetCore.Configuration.Secrets** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="68d1a-108">Siga estos pasos para empezar a usar secretos de Azure Key Vault:</span><span class="sxs-lookup"><span data-stu-id="68d1a-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="68d1a-109">Registre la aplicación como una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="68d1a-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="68d1a-110">(el acceso a los almacenes de claves se administra mediante Azure AD). Puede hacerlo a través del portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="68d1a-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>\

   <span data-ttu-id="68d1a-111">Como alternativa, si quiere que la aplicación se autentique mediante un certificado en lugar de hacerlo con una contraseña o un secreto de cliente, puede usar el cmdlet de PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication).</span><span class="sxs-lookup"><span data-stu-id="68d1a-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="68d1a-112">El certificado que registre en Azure Key Vault solo necesita su clave pública</span><span class="sxs-lookup"><span data-stu-id="68d1a-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="68d1a-113">La aplicación usará la clave privada.</span><span class="sxs-lookup"><span data-stu-id="68d1a-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="68d1a-114">Conceda a la aplicación registrada acceso al almacén de claves creando una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="68d1a-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="68d1a-115">Puede hacerlo usando los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68d1a-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="68d1a-116">Incluya el almacén de claves como origen de configuración en la aplicación mediante la llamada al método de extensión AzureKeyVaultConfigurationExtensions.AddAzureKeyVault cuando cree una instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.</span><span class="sxs-lookup"><span data-stu-id="68d1a-116">Include the key vault as a configuration source in your application by calling the AzureKeyVaultConfigurationExtensions.AddAzureKeyVault extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span>

<span data-ttu-id="68d1a-117">Tenga en cuenta que, al llamar a `AddAzureKeyVault` necesitará el Id. de la aplicación registrada y a la que se concedió acceso al almacén de claves en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="68d1a-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span> <span data-ttu-id="68d1a-118">O bien, primero puede ejecutar el comando de la CLI de Azure `az login` y, después, usar una sobrecarga de `AddAzureKeyVault` que toma un objeto DefaultAzureCredential en lugar del cliente.</span><span class="sxs-lookup"><span data-stu-id="68d1a-118">Or you can firstly running the Azure CLI command: `az login`, then using an overload of `AddAzureKeyVault` that takes a DefaultAzureCredential in place of the client.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68d1a-119">Le recomendamos que registre Azure Key Vault como el último proveedor de configuración para que pueda invalidar los valores de configuración de proveedores anteriores.</span><span class="sxs-lookup"><span data-stu-id="68d1a-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="68d1a-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="68d1a-120">Additional resources</span></span>

- <span data-ttu-id="68d1a-121">**Using Azure Key Vault to protect application secrets (Usar Azure Key Vault para proteger secretos de aplicaciones)**  </span><span class="sxs-lookup"><span data-stu-id="68d1a-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/architecture/multitenant-identity](/azure/architecture/multitenant-identity-keyvault)

- <span data-ttu-id="68d1a-122">**Safe storage of app secrets during development (Almacenamiento seguro de secretos de aplicación durante el desarrollo)**  </span><span class="sxs-lookup"><span data-stu-id="68d1a-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="68d1a-123">**Configuring data protection (Configuración de la protección de datos)**  </span><span class="sxs-lookup"><span data-stu-id="68d1a-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="68d1a-124">**Administración y duración de las claves de protección de datos en ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="68d1a-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="68d1a-125">Repositorio de GitHub **Microsoft.Extensions.Configuration**.</span><span class="sxs-lookup"><span data-stu-id="68d1a-125">**Microsoft.Extensions.Configuration** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration>

>[!div class="step-by-step"]
><span data-ttu-id="68d1a-126">[Anterior](developer-app-secrets-storage.md)
>[Siguiente](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="68d1a-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
