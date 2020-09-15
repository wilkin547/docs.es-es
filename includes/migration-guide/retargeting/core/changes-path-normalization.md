---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614689"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="0ab41-101">Cambios en la normalización de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="0ab41-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="0ab41-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ab41-102">Details</span></span>

<span data-ttu-id="0ab41-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, ha cambiado la forma en que el entorno de ejecución normaliza las rutas de acceso. La normalización de una ruta de acceso implica la modificación de la cadena que identifica una ruta de acceso o un archivo para que se ajuste a una ruta de acceso válida en el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="0ab41-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="0ab41-104">La normalización implica normalmente:</span><span class="sxs-lookup"><span data-stu-id="0ab41-104">Normalization typically involves:</span></span>

- <span data-ttu-id="0ab41-105">La canonicalización del componente y los separadores de directorios.</span><span class="sxs-lookup"><span data-stu-id="0ab41-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="0ab41-106">La aplicación del directorio actual en una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="0ab41-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="0ab41-107">La evaluación del directorio relativo (.) o el directorio principal (..) en una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ab41-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="0ab41-108">El recorte de caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="0ab41-108">Trimming specified characters.</span></span>
<span data-ttu-id="0ab41-109">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, los cambios siguientes en la normalización de la ruta de acceso están habilitados de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="0ab41-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="0ab41-110">El tiempo de ejecución se aplaza para la función [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) del sistema operativo con el objetivo de normalizar las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ab41-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="0ab41-111">La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).</span><span class="sxs-lookup"><span data-stu-id="0ab41-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="0ab41-112">Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="0ab41-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="0ab41-113">El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ab41-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="0ab41-114">Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.</span><span class="sxs-lookup"><span data-stu-id="0ab41-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="0ab41-115">Estos cambios mejoran el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0ab41-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="0ab41-116">Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o posterior, no se ven afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="0ab41-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0ab41-117">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0ab41-117">Suggestion</span></span>

<span data-ttu-id="0ab41-118">Las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior pueden rechazar este cambio y usar la normalización heredada si agregan lo siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0ab41-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="0ab41-119">Las aplicaciones que tienen como destino .NET Framework 4.6.1 o versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, pueden habilitar los cambios en la normalización de rutas de acceso si se agrega la línea siguiente a la sección `<runtime>` del archivo .configuration de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0ab41-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="0ab41-120">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0ab41-120">Name</span></span>    | <span data-ttu-id="0ab41-121">Valor</span><span class="sxs-lookup"><span data-stu-id="0ab41-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0ab41-122">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0ab41-122">Scope</span></span>   | <span data-ttu-id="0ab41-123">Secundaria</span><span class="sxs-lookup"><span data-stu-id="0ab41-123">Minor</span></span>       |
| <span data-ttu-id="0ab41-124">Versión</span><span class="sxs-lookup"><span data-stu-id="0ab41-124">Version</span></span> | <span data-ttu-id="0ab41-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0ab41-125">4.6.2</span></span>       |
| <span data-ttu-id="0ab41-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ab41-126">Type</span></span>    | <span data-ttu-id="0ab41-127">Redestinación</span><span class="sxs-lookup"><span data-stu-id="0ab41-127">Retargeting</span></span> |
