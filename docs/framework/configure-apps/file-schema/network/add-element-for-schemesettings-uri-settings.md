---
title: "&lt;agregar&gt; elemento para schemeSettings (configuración de Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2d617e78231bd0b9f4e332c4b7fbe58b78598868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="bff82-102">&lt;agregar&gt; elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="bff82-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="bff82-103">Agrega un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="bff82-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="bff82-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bff82-104">\<configuration></span></span>  
<span data-ttu-id="bff82-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="bff82-105">\<uri></span></span>  
<span data-ttu-id="bff82-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="bff82-106">\<schemeSettings></span></span>  
<span data-ttu-id="bff82-107">\<add></span><span class="sxs-lookup"><span data-stu-id="bff82-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff82-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bff82-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bff82-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bff82-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bff82-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bff82-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bff82-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bff82-111">Attributes</span></span>  
  
|<span data-ttu-id="bff82-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="bff82-112">Attribute</span></span>|<span data-ttu-id="bff82-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bff82-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bff82-114">name</span><span class="sxs-lookup"><span data-stu-id="bff82-114">name</span></span>|<span data-ttu-id="bff82-115">El nombre de esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="bff82-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="bff82-116">El solo valores compatibles son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="bff82-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="bff82-117">{Nombre del atributo} Atributo</span><span class="sxs-lookup"><span data-stu-id="bff82-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="bff82-118">Valor</span><span class="sxs-lookup"><span data-stu-id="bff82-118">Value</span></span>|<span data-ttu-id="bff82-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="bff82-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bff82-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="bff82-120">genericUriParserOptions</span></span>|<span data-ttu-id="bff82-121">Las opciones del analizador para este esquema.</span><span class="sxs-lookup"><span data-stu-id="bff82-121">The parser options for this scheme.</span></span> <span data-ttu-id="bff82-122">El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="bff82-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bff82-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bff82-123">Child Elements</span></span>  
 <span data-ttu-id="bff82-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bff82-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bff82-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bff82-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bff82-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bff82-126">Element</span></span>|<span data-ttu-id="bff82-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bff82-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bff82-128">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="bff82-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="bff82-129">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="bff82-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bff82-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bff82-130">Remarks</span></span>  
 <span data-ttu-id="bff82-131">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de la codificación de porcentaje de quitar los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bff82-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="bff82-132">Esto se implementa como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bff82-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="bff82-133">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría producir en el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="bff82-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="bff82-134">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primera delimitadores de ruta de acceso de los caracteres de escape anular y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bff82-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="bff82-135">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase resultados de constructor en el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="bff82-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="bff82-136">Este comportamiento predeterminado puede modificarse para no anula escape porcentaje de ruta de acceso codificada de los delimitadores con la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="bff82-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bff82-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bff82-137">Configuration Files</span></span>  
 <span data-ttu-id="bff82-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bff82-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bff82-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bff82-139">Example</span></span>  
 <span data-ttu-id="bff82-140">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="bff82-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bff82-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bff82-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="bff82-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bff82-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
