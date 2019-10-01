---
title: Elemento <clear> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: e954fef455d0279a945c33f2014913fea9d63064
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699442"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="fd066-102">\<clear > elemento de schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="fd066-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="fd066-103">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="fd066-103">Clears all existing scheme settings.</span></span>  
  
[<span data-ttu-id="fd066-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="fd066-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fd066-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd066-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="fd066-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd066-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="fd066-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="fd066-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd066-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd066-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd066-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd066-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd066-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd066-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd066-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd066-111">Attributes</span></span>  
 <span data-ttu-id="fd066-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd066-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd066-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd066-113">Child Elements</span></span>  
 <span data-ttu-id="fd066-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd066-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd066-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd066-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fd066-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd066-116">Element</span></span>|<span data-ttu-id="fd066-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd066-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd066-118">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="fd066-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="fd066-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="fd066-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd066-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd066-120">Remarks</span></span>  
 <span data-ttu-id="fd066-121">De forma predeterminada, la clase <xref:System.Uri?displayProperty=nameWithType> quita los caracteres de escape de los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="fd066-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="fd066-122">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd066-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="fd066-123">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fd066-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="fd066-124">Por este motivo, la clase <xref:System.Uri?displayProperty=nameWithType> primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="fd066-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="fd066-125">El resultado de pasar la dirección URL malintencionada anterior al constructor de clase <xref:System.Uri?displayProperty=nameWithType> da como resultado el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd066-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="fd066-126">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="fd066-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fd066-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fd066-127">Configuration Files</span></span>  
 <span data-ttu-id="fd066-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fd066-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd066-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd066-129">Example</span></span>  
 <span data-ttu-id="fd066-130">En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> que borra todas las configuraciones de esquema y, a continuación, agrega compatibilidad para no escapar delimitadores de ruta de acceso con codificación porcentual para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="fd066-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd066-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd066-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="fd066-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="fd066-132">Network Settings Schema</span></span>](index.md)
