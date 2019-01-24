---
title: '&lt;agregar&gt; elemento para schemeSettings (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: d64744cf3c88d5ec0f0edf1a31cdf184c3c8277e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524109"
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="3e844-102">&lt;agregar&gt; elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="3e844-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="3e844-103">Agrega un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="3e844-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="3e844-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e844-104">\<configuration></span></span>  
<span data-ttu-id="3e844-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="3e844-105">\<uri></span></span>  
<span data-ttu-id="3e844-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="3e844-106">\<schemeSettings></span></span>  
<span data-ttu-id="3e844-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3e844-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e844-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e844-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e844-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e844-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3e844-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e844-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e844-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e844-111">Attributes</span></span>  
  
|<span data-ttu-id="3e844-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e844-112">Attribute</span></span>|<span data-ttu-id="3e844-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e844-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e844-114">name</span><span class="sxs-lookup"><span data-stu-id="3e844-114">name</span></span>|<span data-ttu-id="3e844-115">El nombre de esquema que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="3e844-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="3e844-116">Los únicos valores compatibles son el nombre = "http" y el nombre = "https".</span><span class="sxs-lookup"><span data-stu-id="3e844-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="3e844-117">{Nombre del atributo} Atributo</span><span class="sxs-lookup"><span data-stu-id="3e844-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="3e844-118">Valor</span><span class="sxs-lookup"><span data-stu-id="3e844-118">Value</span></span>|<span data-ttu-id="3e844-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e844-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e844-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="3e844-120">genericUriParserOptions</span></span>|<span data-ttu-id="3e844-121">Las opciones del analizador de este esquema.</span><span class="sxs-lookup"><span data-stu-id="3e844-121">The parser options for this scheme.</span></span> <span data-ttu-id="3e844-122">El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="3e844-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e844-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e844-123">Child Elements</span></span>  
 <span data-ttu-id="3e844-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3e844-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e844-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e844-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3e844-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e844-126">Element</span></span>|<span data-ttu-id="3e844-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e844-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e844-128">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="3e844-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="3e844-129">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="3e844-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e844-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e844-130">Remarks</span></span>  
 <span data-ttu-id="3e844-131">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3e844-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3e844-132">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e844-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3e844-133">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="3e844-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3e844-134">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3e844-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3e844-135">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="3e844-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3e844-136">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="3e844-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3e844-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3e844-137">Configuration Files</span></span>  
 <span data-ttu-id="3e844-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3e844-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e844-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e844-139">Example</span></span>  
 <span data-ttu-id="3e844-140">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir los delimitadores de ruta de acceso codificados con porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="3e844-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e844-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e844-141">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="3e844-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="3e844-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
