---
title: '&lt;quitar&gt; elemento para schemeSettings (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3f4e3dbdc3dae425e44cd1c0890e8fef9d42a780
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028405"
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="81116-102">&lt;quitar&gt; elemento para schemeSettings (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="81116-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="81116-103">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="81116-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="81116-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="81116-104">\<configuration></span></span>  
<span data-ttu-id="81116-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="81116-105">\<uri></span></span>  
<span data-ttu-id="81116-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="81116-106">\<schemeSettings></span></span>  
<span data-ttu-id="81116-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="81116-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81116-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81116-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81116-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="81116-109">Attributes and Elements</span></span>  
 <span data-ttu-id="81116-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="81116-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81116-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="81116-111">Attributes</span></span>  
  
|<span data-ttu-id="81116-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="81116-112">Attribute</span></span>|<span data-ttu-id="81116-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="81116-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81116-114">name</span><span class="sxs-lookup"><span data-stu-id="81116-114">name</span></span>|<span data-ttu-id="81116-115">El nombre de esquema que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="81116-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="81116-116">Los únicos valores compatibles son el nombre = "http" y el nombre = "https".</span><span class="sxs-lookup"><span data-stu-id="81116-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81116-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="81116-117">Child Elements</span></span>  
 <span data-ttu-id="81116-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="81116-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81116-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="81116-119">Parent Elements</span></span>  
  
|<span data-ttu-id="81116-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="81116-120">Element</span></span>|<span data-ttu-id="81116-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="81116-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81116-122">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="81116-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="81116-123">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="81116-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81116-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81116-124">Remarks</span></span>  
 <span data-ttu-id="81116-125">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="81116-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="81116-126">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="81116-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="81116-127">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="81116-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="81116-128">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="81116-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="81116-129">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="81116-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="81116-130">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="81116-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="81116-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="81116-131">Configuration Files</span></span>  
 <span data-ttu-id="81116-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="81116-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81116-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81116-133">Example</span></span>  
 <span data-ttu-id="81116-134">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase que quita cualquier configuración de esquema para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="81116-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81116-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="81116-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="81116-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="81116-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
