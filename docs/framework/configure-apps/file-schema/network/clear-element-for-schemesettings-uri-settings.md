---
title: Elemento <clear> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664172"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="e876e-102">\<borrar > elemento para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="e876e-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="e876e-103">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="e876e-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="e876e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e876e-104">\<configuration></span></span>  
<span data-ttu-id="e876e-105">\<Uri ></span><span class="sxs-lookup"><span data-stu-id="e876e-105">\<uri></span></span>  
<span data-ttu-id="e876e-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="e876e-106">\<schemeSettings></span></span>  
<span data-ttu-id="e876e-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="e876e-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e876e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e876e-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e876e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e876e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e876e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e876e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e876e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e876e-111">Attributes</span></span>  
 <span data-ttu-id="e876e-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e876e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e876e-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e876e-113">Child Elements</span></span>  
 <span data-ttu-id="e876e-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e876e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e876e-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e876e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e876e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e876e-116">Element</span></span>|<span data-ttu-id="e876e-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e876e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e876e-118">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="e876e-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="e876e-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="e876e-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e876e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e876e-120">Remarks</span></span>  
 <span data-ttu-id="e876e-121">De forma predeterminada, <xref:System.Uri?displayProperty=nameWithType> la clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e876e-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="e876e-122">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e876e-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="e876e-123">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e876e-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="e876e-124">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> la clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e876e-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="e876e-125">El resultado de pasar la dirección URL malintencionada anterior <xref:System.Uri?displayProperty=nameWithType> al constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="e876e-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="e876e-126">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="e876e-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e876e-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e876e-127">Configuration Files</span></span>  
 <span data-ttu-id="e876e-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e876e-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e876e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e876e-129">Example</span></span>  
 <span data-ttu-id="e876e-130">En el ejemplo siguiente se muestra una configuración utilizada <xref:System.Uri> por la clase que borra todas las configuraciones de esquema y, a continuación, agrega compatibilidad para no escapar delimitadores de ruta de acceso codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="e876e-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e876e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e876e-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="e876e-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e876e-132">Network Settings Schema</span></span>](index.md)
