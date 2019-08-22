---
title: Elemento <remove> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 4a891eb8a2fd2d66b6435e2ae774ecd4a157c0f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659218"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="73c0f-102">\<quitar > elemento de schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="73c0f-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="73c0f-103">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="73c0f-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="73c0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73c0f-104">\<configuration></span></span>  
<span data-ttu-id="73c0f-105">\<Uri ></span><span class="sxs-lookup"><span data-stu-id="73c0f-105">\<uri></span></span>  
<span data-ttu-id="73c0f-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="73c0f-106">\<schemeSettings></span></span>  
<span data-ttu-id="73c0f-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="73c0f-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c0f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73c0f-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73c0f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73c0f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73c0f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73c0f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73c0f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="73c0f-111">Attributes</span></span>  
  
|<span data-ttu-id="73c0f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="73c0f-112">Attribute</span></span>|<span data-ttu-id="73c0f-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73c0f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73c0f-114">name</span><span class="sxs-lookup"><span data-stu-id="73c0f-114">name</span></span>|<span data-ttu-id="73c0f-115">Nombre del esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="73c0f-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="73c0f-116">Los únicos valores admitidos son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="73c0f-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73c0f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73c0f-117">Child Elements</span></span>  
 <span data-ttu-id="73c0f-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73c0f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73c0f-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73c0f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="73c0f-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="73c0f-120">Element</span></span>|<span data-ttu-id="73c0f-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73c0f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73c0f-122">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="73c0f-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="73c0f-123">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="73c0f-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73c0f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73c0f-124">Remarks</span></span>  
 <span data-ttu-id="73c0f-125">De forma predeterminada, <xref:System.Uri?displayProperty=nameWithType> la clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="73c0f-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="73c0f-126">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="73c0f-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="73c0f-127">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="73c0f-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="73c0f-128">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> la clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="73c0f-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="73c0f-129">El resultado de pasar la dirección URL malintencionada anterior <xref:System.Uri?displayProperty=nameWithType> al constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="73c0f-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="73c0f-130">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="73c0f-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73c0f-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="73c0f-131">Configuration Files</span></span>  
 <span data-ttu-id="73c0f-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="73c0f-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c0f-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73c0f-133">Example</span></span>  
 <span data-ttu-id="73c0f-134">En el ejemplo siguiente se muestra una configuración utilizada <xref:System.Uri> por la clase que quita cualquier configuración de esquema para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="73c0f-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73c0f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c0f-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="73c0f-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="73c0f-136">Network Settings Schema</span></span>](index.md)
