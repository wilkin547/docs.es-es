---
title: <add> Elemento para schemeSettings (configuración de Uri)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: e7606a1185d406384a926ca4dcb7c42586461574
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139937"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="7ab36-102">\<Agregar > elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="7ab36-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="7ab36-103">Agrega un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="7ab36-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="7ab36-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7ab36-104">\<configuration></span></span>  
<span data-ttu-id="7ab36-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="7ab36-105">\<uri></span></span>  
<span data-ttu-id="7ab36-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="7ab36-106">\<schemeSettings></span></span>  
<span data-ttu-id="7ab36-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7ab36-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab36-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ab36-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ab36-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ab36-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ab36-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ab36-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ab36-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ab36-111">Attributes</span></span>  
  
|<span data-ttu-id="7ab36-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ab36-112">Attribute</span></span>|<span data-ttu-id="7ab36-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ab36-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ab36-114">name</span><span class="sxs-lookup"><span data-stu-id="7ab36-114">name</span></span>|<span data-ttu-id="7ab36-115">El nombre de esquema que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="7ab36-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="7ab36-116">Los únicos valores compatibles son el nombre = "http" y el nombre = "https".</span><span class="sxs-lookup"><span data-stu-id="7ab36-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="7ab36-117">{Nombre del atributo} Atributo</span><span class="sxs-lookup"><span data-stu-id="7ab36-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="7ab36-118">Valor</span><span class="sxs-lookup"><span data-stu-id="7ab36-118">Value</span></span>|<span data-ttu-id="7ab36-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ab36-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ab36-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="7ab36-120">genericUriParserOptions</span></span>|<span data-ttu-id="7ab36-121">Las opciones del analizador de este esquema.</span><span class="sxs-lookup"><span data-stu-id="7ab36-121">The parser options for this scheme.</span></span> <span data-ttu-id="7ab36-122">El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="7ab36-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ab36-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ab36-123">Child Elements</span></span>  
 <span data-ttu-id="7ab36-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7ab36-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ab36-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ab36-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7ab36-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ab36-126">Element</span></span>|<span data-ttu-id="7ab36-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ab36-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ab36-128">\<schemeSettings > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="7ab36-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="7ab36-129">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="7ab36-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab36-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ab36-130">Remarks</span></span>  
 <span data-ttu-id="7ab36-131">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ab36-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="7ab36-132">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ab36-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7ab36-133">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="7ab36-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="7ab36-134">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ab36-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="7ab36-135">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="7ab36-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7ab36-136">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="7ab36-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7ab36-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7ab36-137">Configuration Files</span></span>  
 <span data-ttu-id="7ab36-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7ab36-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ab36-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ab36-139">Example</span></span>  
 <span data-ttu-id="7ab36-140">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir los delimitadores de ruta de acceso codificados con porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="7ab36-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ab36-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ab36-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="7ab36-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="7ab36-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
