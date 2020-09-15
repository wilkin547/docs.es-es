---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614665"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="97b7e-101">Asegurarse de que System.Uri usa un juego de caracteres reservados coherente</span><span class="sxs-lookup"><span data-stu-id="97b7e-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="97b7e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="97b7e-102">Details</span></span>

<span data-ttu-id="97b7e-103">En <xref:System.Uri?displayProperty=fullName>, algunos caracteres codificados por porcentaje que en ocasiones se descodificaban ahora se dejan sin codificar de manera constante.</span><span class="sxs-lookup"><span data-stu-id="97b7e-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="97b7e-104">Esto se produce en las propiedades y métodos que tienen acceso a los componentes de ruta de acceso, consulta, fragmento o información de usuario del URI.</span><span class="sxs-lookup"><span data-stu-id="97b7e-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="97b7e-105">El comportamiento solo cambiará cuando se cumplen las dos acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="97b7e-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="97b7e-106">El URI contiene el formato codificado de cualquiera de los caracteres reservados siguientes: `:`, `'`, `(`, `)`, `!` o `*`.</span><span class="sxs-lookup"><span data-stu-id="97b7e-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="97b7e-107">El URI contiene un carácter no reservado codificado o Unicode.</span><span class="sxs-lookup"><span data-stu-id="97b7e-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="97b7e-108">Si se cumplen las dos condiciones anteriores, los caracteres reservados codificados se dejan codificados.</span><span class="sxs-lookup"><span data-stu-id="97b7e-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="97b7e-109">En versiones anteriores de .NET Framework se descodificaban.</span><span class="sxs-lookup"><span data-stu-id="97b7e-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="97b7e-110">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="97b7e-110">Suggestion</span></span>

<span data-ttu-id="97b7e-111">Para las aplicaciones destinadas a versiones de .NET Framework a partir de 4.7.2, el nuevo comportamiento de descodificación está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97b7e-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="97b7e-112">Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="97b7e-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="97b7e-113">Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, el comportamiento de descodificación nuevo está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97b7e-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="97b7e-114">Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="97b7e-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="97b7e-115">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="97b7e-115">Name</span></span>    | <span data-ttu-id="97b7e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="97b7e-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="97b7e-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="97b7e-117">Scope</span></span>   | <span data-ttu-id="97b7e-118">Secundaria</span><span class="sxs-lookup"><span data-stu-id="97b7e-118">Minor</span></span>       |
| <span data-ttu-id="97b7e-119">Versión</span><span class="sxs-lookup"><span data-stu-id="97b7e-119">Version</span></span> | <span data-ttu-id="97b7e-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="97b7e-120">4.7.2</span></span>       |
| <span data-ttu-id="97b7e-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="97b7e-121">Type</span></span>    | <span data-ttu-id="97b7e-122">Redestinación</span><span class="sxs-lookup"><span data-stu-id="97b7e-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="97b7e-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="97b7e-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
