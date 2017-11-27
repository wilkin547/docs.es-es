---
title: "&lt;schemeSettings&gt; elemento (configuración de Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4cf1d2013a51985f9d7772ac0ef86e5dbb120be9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="38ee8-102">&lt;schemeSettings&gt; elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="38ee8-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="38ee8-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="38ee8-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="38ee8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38ee8-104">\<configuration></span></span>  
<span data-ttu-id="38ee8-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="38ee8-105">\<uri></span></span>  
<span data-ttu-id="38ee8-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="38ee8-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ee8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38ee8-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38ee8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38ee8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="38ee8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38ee8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38ee8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="38ee8-110">Attributes</span></span>  
 <span data-ttu-id="38ee8-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="38ee8-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38ee8-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38ee8-112">Child Elements</span></span>  
  
|<span data-ttu-id="38ee8-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="38ee8-113">**Element**</span></span>|<span data-ttu-id="38ee8-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="38ee8-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38ee8-115">add</span><span class="sxs-lookup"><span data-stu-id="38ee8-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="38ee8-116">Agrega un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="38ee8-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="38ee8-117">clear</span><span class="sxs-lookup"><span data-stu-id="38ee8-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="38ee8-118">Borra todos los valores de esquema existente.</span><span class="sxs-lookup"><span data-stu-id="38ee8-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="38ee8-119">remove</span><span class="sxs-lookup"><span data-stu-id="38ee8-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="38ee8-120">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="38ee8-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38ee8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38ee8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="38ee8-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="38ee8-122">**Element**</span></span>|<span data-ttu-id="38ee8-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="38ee8-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38ee8-124">URI</span><span class="sxs-lookup"><span data-stu-id="38ee8-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="38ee8-125">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="38ee8-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ee8-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38ee8-126">Remarks</span></span>  
 <span data-ttu-id="38ee8-127">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de la codificación de porcentaje de quitar los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="38ee8-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="38ee8-128">Esto se implementa como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="38ee8-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="38ee8-129">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría producir en el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="38ee8-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="38ee8-130">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primera delimitadores de ruta de acceso de los caracteres de escape anular y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="38ee8-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="38ee8-131">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase resultados de constructor en el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="38ee8-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="38ee8-132">Este comportamiento predeterminado puede modificarse para no anula escape porcentaje de ruta de acceso codificada de los delimitadores con la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="38ee8-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="38ee8-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="38ee8-133">Configuration Files</span></span>  
 <span data-ttu-id="38ee8-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="38ee8-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ee8-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38ee8-135">Example</span></span>  
 <span data-ttu-id="38ee8-136">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="38ee8-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="38ee8-137">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="38ee8-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="38ee8-138">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="38ee8-138">Namespace</span></span>|<span data-ttu-id="38ee8-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="38ee8-139">System</span></span>|  
|<span data-ttu-id="38ee8-140">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="38ee8-140">Schema Name</span></span>||  
|<span data-ttu-id="38ee8-141">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="38ee8-141">Validation File</span></span>||  
|<span data-ttu-id="38ee8-142">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="38ee8-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="38ee8-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="38ee8-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="38ee8-144">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="38ee8-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
