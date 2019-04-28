---
title: Elemento <remove> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: f29ee86deaa150324b40f4fac12ead152553e50d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674446"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="4ac1e-102">\<Quitar > elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="4ac1e-103">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="4ac1e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ac1e-104">\<configuration></span></span>  
<span data-ttu-id="4ac1e-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="4ac1e-105">\<uri></span></span>  
<span data-ttu-id="4ac1e-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="4ac1e-106">\<schemeSettings></span></span>  
<span data-ttu-id="4ac1e-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="4ac1e-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac1e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ac1e-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ac1e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ac1e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ac1e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ac1e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ac1e-111">Attributes</span></span>  
  
|<span data-ttu-id="4ac1e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ac1e-112">Attribute</span></span>|<span data-ttu-id="4ac1e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ac1e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ac1e-114">name</span><span class="sxs-lookup"><span data-stu-id="4ac1e-114">name</span></span>|<span data-ttu-id="4ac1e-115">El nombre de esquema que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="4ac1e-116">Los únicos valores compatibles son el nombre = "http" y el nombre = "https".</span><span class="sxs-lookup"><span data-stu-id="4ac1e-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ac1e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ac1e-117">Child Elements</span></span>  
 <span data-ttu-id="4ac1e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ac1e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ac1e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4ac1e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ac1e-120">Element</span></span>|<span data-ttu-id="4ac1e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ac1e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ac1e-122">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="4ac1e-123">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ac1e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ac1e-124">Remarks</span></span>  
 <span data-ttu-id="4ac1e-125">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="4ac1e-126">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4ac1e-127">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="4ac1e-128">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="4ac1e-129">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4ac1e-130">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4ac1e-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4ac1e-131">Configuration Files</span></span>  
 <span data-ttu-id="4ac1e-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4ac1e-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ac1e-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ac1e-133">Example</span></span>  
 <span data-ttu-id="4ac1e-134">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase que quita cualquier configuración de esquema para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ac1e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ac1e-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="4ac1e-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4ac1e-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
