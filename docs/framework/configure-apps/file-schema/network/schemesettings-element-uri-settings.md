---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697770"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="f387a-102">\<elemento > schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="f387a-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="f387a-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="f387a-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="f387a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f387a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f387a-105">&nbsp;[ **uri de\<&nbsp;>** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f387a-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="f387a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<schemeSettings >**</span><span class="sxs-lookup"><span data-stu-id="f387a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f387a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f387a-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f387a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f387a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f387a-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f387a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f387a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f387a-110">Attributes</span></span>  
 <span data-ttu-id="f387a-111">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f387a-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f387a-112">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="f387a-112">Child Elements</span></span>  
  
|<span data-ttu-id="f387a-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="f387a-113">**Element**</span></span>|<span data-ttu-id="f387a-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f387a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f387a-115">add</span><span class="sxs-lookup"><span data-stu-id="f387a-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f387a-116">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="f387a-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="f387a-117">clear</span><span class="sxs-lookup"><span data-stu-id="f387a-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f387a-118">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="f387a-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="f387a-119">remove</span><span class="sxs-lookup"><span data-stu-id="f387a-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f387a-120">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="f387a-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f387a-121">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="f387a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f387a-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="f387a-122">**Element**</span></span>|<span data-ttu-id="f387a-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f387a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f387a-124">uri</span><span class="sxs-lookup"><span data-stu-id="f387a-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="f387a-125">Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="f387a-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f387a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f387a-126">Remarks</span></span>  
 <span data-ttu-id="f387a-127">De forma predeterminada, la clase <xref:System.Uri?displayProperty=nameWithType> no aplica el escape a los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f387a-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="f387a-128">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f387a-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f387a-129">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f387a-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="f387a-130">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primero quita los caracteres de escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f387a-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="f387a-131">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f387a-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f387a-132">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="f387a-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f387a-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f387a-133">Configuration Files</span></span>  
 <span data-ttu-id="f387a-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f387a-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f387a-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f387a-135">Example</span></span>  
 <span data-ttu-id="f387a-136">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir los delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="f387a-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="f387a-137">Información del elemento</span><span class="sxs-lookup"><span data-stu-id="f387a-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="f387a-138">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f387a-138">Namespace</span></span>|<span data-ttu-id="f387a-139">System</span><span class="sxs-lookup"><span data-stu-id="f387a-139">System</span></span>|  
|<span data-ttu-id="f387a-140">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="f387a-140">Schema Name</span></span>||  
|<span data-ttu-id="f387a-141">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="f387a-141">Validation File</span></span>||  
|<span data-ttu-id="f387a-142">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="f387a-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="f387a-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="f387a-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="f387a-144">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f387a-144">Network Settings Schema</span></span>](index.md)
