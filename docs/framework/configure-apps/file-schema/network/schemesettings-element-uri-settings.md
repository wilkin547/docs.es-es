---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154652"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="48af5-102">\<Elemento schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="48af5-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="48af5-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="48af5-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="48af5-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="48af5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="48af5-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="48af5-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="48af5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span><span class="sxs-lookup"><span data-stu-id="48af5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48af5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48af5-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48af5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48af5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48af5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48af5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48af5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="48af5-110">Attributes</span></span>  
 <span data-ttu-id="48af5-111">None</span><span class="sxs-lookup"><span data-stu-id="48af5-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48af5-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48af5-112">Child Elements</span></span>  
  
|<span data-ttu-id="48af5-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="48af5-113">**Element**</span></span>|<span data-ttu-id="48af5-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="48af5-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48af5-115">agregar</span><span class="sxs-lookup"><span data-stu-id="48af5-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="48af5-116">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="48af5-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="48af5-117">Claro</span><span class="sxs-lookup"><span data-stu-id="48af5-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="48af5-118">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="48af5-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="48af5-119">quitar</span><span class="sxs-lookup"><span data-stu-id="48af5-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="48af5-120">Quita una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="48af5-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48af5-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48af5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="48af5-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="48af5-122">**Element**</span></span>|<span data-ttu-id="48af5-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="48af5-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48af5-124">Uri</span><span class="sxs-lookup"><span data-stu-id="48af5-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="48af5-125">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores de recursos uniformes (URI).</span><span class="sxs-lookup"><span data-stu-id="48af5-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48af5-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48af5-126">Remarks</span></span>  
 <span data-ttu-id="48af5-127">De forma <xref:System.Uri?displayProperty=nameWithType> predeterminada, la clase desestrata delimitadores de ruta de acceso con codificación porcentual antes de ejecutar la compresión de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="48af5-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="48af5-128">Esto se implementó como un mecanismo de seguridad contra ataques como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="48af5-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="48af5-129">Si este URI se pasa a módulos que no controlan correctamente los caracteres codificados porcentuales, podría dar lugar a que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="48af5-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="48af5-130">Por este <xref:System.Uri?displayProperty=nameWithType> motivo, la clase primero anula los delimitadores de ruta de acceso y, a continuación, aplica la compresión de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="48af5-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="48af5-131">El resultado de pasar la <xref:System.Uri?displayProperty=nameWithType> dirección URL malintencionada anterior al constructor de clase da como resultado el uri siguiente:</span><span class="sxs-lookup"><span data-stu-id="48af5-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="48af5-132">Este comportamiento predeterminado se puede modificar para no anular el escape de delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="48af5-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="48af5-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="48af5-133">Configuration Files</span></span>  
 <span data-ttu-id="48af5-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="48af5-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48af5-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48af5-135">Example</span></span>  
 <span data-ttu-id="48af5-136">En el ejemplo siguiente se <xref:System.Uri> muestra una configuración utilizada por la clase para admitir no escapar los delimitadores de ruta codificados porcentuales para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="48af5-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="48af5-137">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="48af5-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="48af5-138">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="48af5-138">Namespace</span></span>|<span data-ttu-id="48af5-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="48af5-139">System</span></span>|  
|<span data-ttu-id="48af5-140">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="48af5-140">Schema Name</span></span>||  
|<span data-ttu-id="48af5-141">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="48af5-141">Validation File</span></span>||  
|<span data-ttu-id="48af5-142">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="48af5-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="48af5-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48af5-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="48af5-144">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="48af5-144">Network Settings Schema</span></span>](index.md)
