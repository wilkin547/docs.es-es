---
title: Elemento <clear> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087437"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="aa0f6-102">Elemento \<clear> para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="aa0f6-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="aa0f6-103">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="aa0f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa0f6-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa0f6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aa0f6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="aa0f6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa0f6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa0f6-107">Attributes</span></span>  
 <span data-ttu-id="aa0f6-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa0f6-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa0f6-109">Child Elements</span></span>  
 <span data-ttu-id="aa0f6-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa0f6-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aa0f6-111">Parent Elements</span></span>  
  
|<span data-ttu-id="aa0f6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa0f6-112">Element</span></span>|<span data-ttu-id="aa0f6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa0f6-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa0f6-114">\<schemeSettings>Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="aa0f6-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="aa0f6-115">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa0f6-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa0f6-116">Remarks</span></span>  
 <span data-ttu-id="aa0f6-117">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="aa0f6-118">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa0f6-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="aa0f6-119">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="aa0f6-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="aa0f6-120">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="aa0f6-121">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="aa0f6-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="aa0f6-122">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="aa0f6-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="aa0f6-123">Configuration Files</span></span>  
 <span data-ttu-id="aa0f6-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="aa0f6-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa0f6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa0f6-125">Example</span></span>  
 <span data-ttu-id="aa0f6-126">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase que borra todas las configuraciones de esquema y, a continuación, agrega compatibilidad para no escapar delimitadores de ruta de acceso codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="aa0f6-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa0f6-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa0f6-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="aa0f6-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="aa0f6-128">Network Settings Schema</span></span>](index.md)
