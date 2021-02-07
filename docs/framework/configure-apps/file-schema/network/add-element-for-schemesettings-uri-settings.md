---
description: 'Más información sobre: <add> elemento para schemeSettings (configuración de URI)'
title: Elemento <add> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: c372577af1c7fbfe669455b50c8b55c82da4fc52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698626"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="c2799-103">Elemento \<add> para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="c2799-103">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="c2799-104">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="c2799-104">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="c2799-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2799-105">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2799-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2799-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c2799-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2799-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2799-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2799-108">Attributes</span></span>  
  
|<span data-ttu-id="c2799-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c2799-109">Attribute</span></span>|<span data-ttu-id="c2799-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2799-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2799-111">name</span><span class="sxs-lookup"><span data-stu-id="c2799-111">name</span></span>|<span data-ttu-id="c2799-112">Nombre del esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c2799-112">The scheme name for which this setting applies.</span></span> <span data-ttu-id="c2799-113">Los únicos valores admitidos son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="c2799-113">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="c2799-114">{Nombre de atributo} Atribui</span><span class="sxs-lookup"><span data-stu-id="c2799-114">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="c2799-115">Value</span><span class="sxs-lookup"><span data-stu-id="c2799-115">Value</span></span>|<span data-ttu-id="c2799-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2799-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2799-117">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="c2799-117">genericUriParserOptions</span></span>|<span data-ttu-id="c2799-118">Opciones del analizador para este esquema.</span><span class="sxs-lookup"><span data-stu-id="c2799-118">The parser options for this scheme.</span></span> <span data-ttu-id="c2799-119">El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="c2799-119">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2799-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2799-120">Child Elements</span></span>  

 <span data-ttu-id="c2799-121">None</span><span class="sxs-lookup"><span data-stu-id="c2799-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2799-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2799-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c2799-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2799-123">Element</span></span>|<span data-ttu-id="c2799-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2799-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2799-125">\<schemeSettings> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="c2799-125">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="c2799-126">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="c2799-126">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2799-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2799-127">Remarks</span></span>  

 <span data-ttu-id="c2799-128">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c2799-128">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="c2799-129">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2799-129">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c2799-130">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c2799-130">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="c2799-131">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c2799-131">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="c2799-132">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="c2799-132">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c2799-133">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="c2799-133">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c2799-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c2799-134">Configuration Files</span></span>  

 <span data-ttu-id="c2799-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c2799-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2799-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2799-136">Example</span></span>  

 <span data-ttu-id="c2799-137">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="c2799-137">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2799-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2799-138">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="c2799-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c2799-139">Network Settings Schema</span></span>](index.md)
