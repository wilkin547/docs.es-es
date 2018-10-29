---
title: '&lt;Borrar&gt; elemento para schemeSettings (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 043ce78283c42d2cf42851e13919bf71a77b28b4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196679"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="a8c04-102">&lt;Borrar&gt; elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="a8c04-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="a8c04-103">Borra todos los valores de esquema existente.</span><span class="sxs-lookup"><span data-stu-id="a8c04-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="a8c04-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a8c04-104">\<configuration></span></span>  
<span data-ttu-id="a8c04-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="a8c04-105">\<uri></span></span>  
<span data-ttu-id="a8c04-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="a8c04-106">\<schemeSettings></span></span>  
<span data-ttu-id="a8c04-107">\<Borrar ></span><span class="sxs-lookup"><span data-stu-id="a8c04-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8c04-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8c04-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8c04-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8c04-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a8c04-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8c04-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8c04-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8c04-111">Attributes</span></span>  
 <span data-ttu-id="a8c04-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8c04-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8c04-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8c04-113">Child Elements</span></span>  
 <span data-ttu-id="a8c04-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8c04-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8c04-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8c04-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a8c04-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8c04-116">Element</span></span>|<span data-ttu-id="a8c04-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c04-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8c04-118">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="a8c04-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="a8c04-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="a8c04-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8c04-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8c04-120">Remarks</span></span>  
 <span data-ttu-id="a8c04-121">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="a8c04-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a8c04-122">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8c04-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a8c04-123">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="a8c04-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a8c04-124">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="a8c04-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a8c04-125">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="a8c04-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a8c04-126">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="a8c04-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a8c04-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8c04-127">Configuration Files</span></span>  
 <span data-ttu-id="a8c04-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a8c04-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8c04-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8c04-129">Example</span></span>  
 <span data-ttu-id="a8c04-130">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase que borra todos los valores de esquema y, a continuación, agrega compatibilidad para delimitadores de ruta de acceso codificados con porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="a8c04-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8c04-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8c04-131">See Also</span></span>  
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
- <xref:System.Uri?displayProperty=nameWithType>  
- [<span data-ttu-id="a8c04-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a8c04-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
