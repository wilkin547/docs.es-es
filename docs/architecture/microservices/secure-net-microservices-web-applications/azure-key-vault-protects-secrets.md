---
title: Usar Azure Key Vault para proteger secretos en tiempo de producción
description: 'Seguridad en microservicios de .NET y aplicaciones web: Azure Key Vault es una forma excelente de gestionar secretos de aplicación controlados en su totalidad por administradores. Los administradores incluso pueden asignar y revocar valores de desarrollo sin necesidad de que los desarrolladores tengan que gestionarlos.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 94243468b35e2db9818ae9afacd5beec0a12075e
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604624"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a>Usar Azure Key Vault para proteger secretos en tiempo de producción

Los secretos almacenados como variables de entorno o almacenados por la herramienta Administrador de secretos todavía se almacenan localmente y se descifran en el equipo. Una opción más segura para almacenar secretos es [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), que proporciona una ubicación central y segura para almacenar claves y secretos.

El paquete **Azure.Extensions.AspNetCore.Configuration.Secrets** permite que una aplicación ASP.NET Core lea información de configuración de Azure Key Vault. Siga estos pasos para empezar a usar secretos de Azure Key Vault:

1. Registre la aplicación como una aplicación de Azure AD. (el acceso a los almacenes de claves se administra mediante Azure AD). Puede hacerlo a través del portal de administración de Azure.\

   Como alternativa, si quiere que la aplicación se autentique mediante un certificado en lugar de hacerlo con una contraseña o un secreto de cliente, puede usar el cmdlet de PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication). El certificado que registre en Azure Key Vault solo necesita su clave pública La aplicación usará la clave privada.

2. Conceda a la aplicación registrada acceso al almacén de claves creando una entidad de servicio. Puede hacerlo usando los siguientes comandos de PowerShell:

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. Incluya el almacén de claves como origen de configuración en la aplicación mediante la llamada al método de extensión AzureKeyVaultConfigurationExtensions.AddAzureKeyVault cuando cree una instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.

Tenga en cuenta que, al llamar a `AddAzureKeyVault` necesitará el Id. de la aplicación registrada y a la que se concedió acceso al almacén de claves en los pasos anteriores. O bien, primero puede ejecutar el comando de la CLI de Azure `az login` y, después, usar una sobrecarga de `AddAzureKeyVault` que toma un objeto DefaultAzureCredential en lugar del cliente.

> [!IMPORTANT]
> Le recomendamos que registre Azure Key Vault como el último proveedor de configuración para que pueda invalidar los valores de configuración de proveedores anteriores.

## <a name="additional-resources"></a>Recursos adicionales

- **Using Azure Key Vault to protect application secrets (Usar Azure Key Vault para proteger secretos de aplicaciones)**  \
  [https://docs.microsoft.com/azure/architecture/multitenant-identity](/azure/architecture/multitenant-identity)

- **Safe storage of app secrets during development (Almacenamiento seguro de secretos de aplicación durante el desarrollo)**  \
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- **Configuring data protection (Configuración de la protección de datos)**  \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- **Administración y duración de las claves de protección de datos en ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

>[!div class="step-by-step"]
>[Anterior](developer-app-secrets-storage.md)
>[Siguiente](../key-takeaways.md)
