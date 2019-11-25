---
title: Elemento <add> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087717"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="425c2-102">\<agregar > elemento para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="425c2-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="425c2-103">Agrega una configuración de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="425c2-103">Adds a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="425c2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="425c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="425c2-105">&nbsp;&nbsp;[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="425c2-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="425c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="425c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="425c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="425c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="425c2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="425c2-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="425c2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="425c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="425c2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="425c2-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="425c2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="425c2-111">Attributes</span></span>  
  
|<span data-ttu-id="425c2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="425c2-112">Attribute</span></span>|<span data-ttu-id="425c2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="425c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="425c2-114">name</span><span class="sxs-lookup"><span data-stu-id="425c2-114">name</span></span>|<span data-ttu-id="425c2-115">Nombre del esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="425c2-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="425c2-116">Los únicos valores admitidos son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="425c2-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="425c2-117">{Nombre de atributo} Atribui</span><span class="sxs-lookup"><span data-stu-id="425c2-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="425c2-118">Valor</span><span class="sxs-lookup"><span data-stu-id="425c2-118">Value</span></span>|<span data-ttu-id="425c2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="425c2-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="425c2-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="425c2-120">genericUriParserOptions</span></span>|<span data-ttu-id="425c2-121">Opciones del analizador para este esquema.</span><span class="sxs-lookup"><span data-stu-id="425c2-121">The parser options for this scheme.</span></span> <span data-ttu-id="425c2-122">El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="425c2-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="425c2-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="425c2-123">Child Elements</span></span>  
 <span data-ttu-id="425c2-124">Ninguno</span><span class="sxs-lookup"><span data-stu-id="425c2-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="425c2-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="425c2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="425c2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="425c2-126">Element</span></span>|<span data-ttu-id="425c2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="425c2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="425c2-128">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="425c2-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="425c2-129">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="425c2-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="425c2-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="425c2-130">Remarks</span></span>  
 <span data-ttu-id="425c2-131">De forma predeterminada, la clase <xref:System.Uri?displayProperty=nameWithType> no aplica el escape a los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="425c2-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="425c2-132">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="425c2-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="425c2-133">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="425c2-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="425c2-134">Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primero quita los caracteres de escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="425c2-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="425c2-135">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="425c2-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="425c2-136">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="425c2-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="425c2-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="425c2-137">Configuration Files</span></span>  
 <span data-ttu-id="425c2-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="425c2-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="425c2-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="425c2-139">Example</span></span>  
 <span data-ttu-id="425c2-140">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir los delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="425c2-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="425c2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="425c2-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="425c2-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="425c2-142">Network Settings Schema</span></span>](index.md)
