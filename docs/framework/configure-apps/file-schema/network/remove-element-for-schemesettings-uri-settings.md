---
description: 'Más información sobre: <remove> elemento para schemeSettings (configuración de URI)'
title: Elemento <remove> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 125a347cfcbb1393ea70032b7e1b198a1a5a4ed0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713031"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="cb4fe-103">Elemento \<remove> para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="cb4fe-103">\<remove> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="cb4fe-104">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-104">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="cb4fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb4fe-105">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb4fe-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cb4fe-106">Attributes and Elements</span></span>  

 <span data-ttu-id="cb4fe-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb4fe-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb4fe-108">Attributes</span></span>  
  
|<span data-ttu-id="cb4fe-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb4fe-109">Attribute</span></span>|<span data-ttu-id="cb4fe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4fe-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb4fe-111">name</span><span class="sxs-lookup"><span data-stu-id="cb4fe-111">name</span></span>|<span data-ttu-id="cb4fe-112">Nombre del esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-112">The scheme name for which this setting applies.</span></span> <span data-ttu-id="cb4fe-113">Los únicos valores admitidos son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="cb4fe-113">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb4fe-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cb4fe-114">Child Elements</span></span>  

 <span data-ttu-id="cb4fe-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb4fe-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb4fe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cb4fe-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb4fe-117">Element</span></span>|<span data-ttu-id="cb4fe-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4fe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb4fe-119">\<schemeSettings> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="cb4fe-119">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="cb4fe-120">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb4fe-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb4fe-121">Remarks</span></span>  

 <span data-ttu-id="cb4fe-122">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-122">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="cb4fe-123">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb4fe-123">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="cb4fe-124">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cb4fe-124">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="cb4fe-125">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-125">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="cb4fe-126">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="cb4fe-126">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="cb4fe-127">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-127">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cb4fe-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cb4fe-128">Configuration Files</span></span>  

 <span data-ttu-id="cb4fe-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cb4fe-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4fe-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb4fe-130">Example</span></span>  

 <span data-ttu-id="cb4fe-131">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase que quita cualquier configuración de esquema para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="cb4fe-131">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb4fe-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb4fe-132">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="cb4fe-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="cb4fe-133">Network Settings Schema</span></span>](index.md)
