---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616290"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="6ddd6-101">Las clases de criptografía administradas no producen una excepción CryptographyException en el modo FIPS</span><span class="sxs-lookup"><span data-stu-id="6ddd6-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="6ddd6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6ddd6-102">Details</span></span>

<span data-ttu-id="6ddd6-103">En NET Framework 4.7.2 y versiones anteriores, las clases del proveedor de servicios criptográficos administrados, como <xref:System.Security.Cryptography.SHA256Managed>, producen una excepción <xref:System.Security.Cryptography.CryptographicException> cuando las bibliotecas criptográficas del sistema están configuradas en modo FIPS.</span><span class="sxs-lookup"><span data-stu-id="6ddd6-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="6ddd6-104">Estas excepciones se producen porque las versiones administradas no han sometido al FIPS (Estándar federal de procesamiento de información) según la certificación 140-2, así como para bloquear los algoritmos criptográficos que no se consideran aprobados según las reglas FIPS.</span><span class="sxs-lookup"><span data-stu-id="6ddd6-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="6ddd6-105">Dado que pocos desarrolladores tienen sus equipos de desarrollo en el modo FIPS, estas excepciones se producen con frecuencia solo en sistemas de producción. Las aplicaciones que tienen como destino .NET Framework 4.8 y versiones posteriores cambian automáticamente a la directiva más reciente y menos estricta, para que ya no se produzca de forma predeterminada <xref:System.Security.Cryptography.CryptographicException> en estos casos.</span><span class="sxs-lookup"><span data-stu-id="6ddd6-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="6ddd6-106">En su lugar, las clases de criptografía administradas redirigen las operaciones criptográficas a una biblioteca de criptografía del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ddd6-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="6ddd6-107">Este cambio de directiva elimina eficazmente una diferencia potencialmente confusa entre entornos de desarrollo y entornos de producción, y permite que componentes nativos y componentes administrados funcionen bajo la misma directiva criptográfica.</span><span class="sxs-lookup"><span data-stu-id="6ddd6-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6ddd6-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6ddd6-108">Suggestion</span></span>

<span data-ttu-id="6ddd6-109">Si no desea este comportamiento, puede dejar de participar en él y restaurar el comportamiento anterior hasta que se produzca <xref:System.Security.Cryptography.CryptographicException> en el modo FIPS agregando la opción de configuración [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6ddd6-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="6ddd6-110">Si la aplicación tiene como destino .NET Framework 4.7.2 o versiones anteriores, se puede también participar en este cambio agregando la opción de configuración [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6ddd6-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="6ddd6-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6ddd6-111">Name</span></span>    | <span data-ttu-id="6ddd6-112">Valor</span><span class="sxs-lookup"><span data-stu-id="6ddd6-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6ddd6-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6ddd6-113">Scope</span></span>   | <span data-ttu-id="6ddd6-114">Borde</span><span class="sxs-lookup"><span data-stu-id="6ddd6-114">Edge</span></span>        |
| <span data-ttu-id="6ddd6-115">Versión</span><span class="sxs-lookup"><span data-stu-id="6ddd6-115">Version</span></span> | <span data-ttu-id="6ddd6-116">4.8</span><span class="sxs-lookup"><span data-stu-id="6ddd6-116">4.8</span></span>         |
| <span data-ttu-id="6ddd6-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ddd6-117">Type</span></span>    | <span data-ttu-id="6ddd6-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6ddd6-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6ddd6-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6ddd6-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
