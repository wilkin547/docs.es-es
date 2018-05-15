---
title: '&lt;Borrar&gt; elemento para schemeSettings (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 32c7a9e07b48536584f7ca5588226fb4479bacb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="120cf-102">&lt;Borrar&gt; elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="120cf-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="120cf-103">Borra todos los valores de esquema existente.</span><span class="sxs-lookup"><span data-stu-id="120cf-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="120cf-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="120cf-104">\<configuration></span></span>  
<span data-ttu-id="120cf-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="120cf-105">\<uri></span></span>  
<span data-ttu-id="120cf-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="120cf-106">\<schemeSettings></span></span>  
<span data-ttu-id="120cf-107">\<Borrar ></span><span class="sxs-lookup"><span data-stu-id="120cf-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120cf-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="120cf-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="120cf-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="120cf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="120cf-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="120cf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="120cf-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="120cf-111">Attributes</span></span>  
 <span data-ttu-id="120cf-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="120cf-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="120cf-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="120cf-113">Child Elements</span></span>  
 <span data-ttu-id="120cf-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="120cf-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="120cf-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="120cf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="120cf-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="120cf-116">Element</span></span>|<span data-ttu-id="120cf-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="120cf-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="120cf-118">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="120cf-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="120cf-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="120cf-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="120cf-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="120cf-120">Remarks</span></span>  
 <span data-ttu-id="120cf-121">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de la codificación de porcentaje de quitar los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="120cf-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="120cf-122">Esto se implementa como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="120cf-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="120cf-123">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría producir en el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="120cf-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="120cf-124">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primera delimitadores de ruta de acceso de los caracteres de escape anular y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="120cf-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="120cf-125">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase resultados de constructor en el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="120cf-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="120cf-126">Este comportamiento predeterminado puede modificarse para no anula escape porcentaje de ruta de acceso codificada de los delimitadores con la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="120cf-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="120cf-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="120cf-127">Configuration Files</span></span>  
 <span data-ttu-id="120cf-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="120cf-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="120cf-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="120cf-129">Example</span></span>  
 <span data-ttu-id="120cf-130">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase que borra todos los valores de esquema y, a continuación, agrega compatibilidad para delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="120cf-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="120cf-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="120cf-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="120cf-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="120cf-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
