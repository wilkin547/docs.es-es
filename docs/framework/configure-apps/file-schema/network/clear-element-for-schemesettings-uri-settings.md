---
title: Elemento <clear> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 17069a56a8647871e98d70826a97a8fe407a0887
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205066"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="951dd-102">Elemento \<clear> para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="951dd-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="951dd-103">Borra todos los valores de esquema existentes.</span><span class="sxs-lookup"><span data-stu-id="951dd-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="951dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="951dd-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="951dd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="951dd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="951dd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="951dd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="951dd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="951dd-107">Attributes</span></span>  

 <span data-ttu-id="951dd-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="951dd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="951dd-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="951dd-109">Child Elements</span></span>  

 <span data-ttu-id="951dd-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="951dd-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="951dd-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="951dd-111">Parent Elements</span></span>  
  
|<span data-ttu-id="951dd-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="951dd-112">Element</span></span>|<span data-ttu-id="951dd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="951dd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="951dd-114">\<schemeSettings> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="951dd-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="951dd-115">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="951dd-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="951dd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="951dd-116">Remarks</span></span>  

 <span data-ttu-id="951dd-117">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="951dd-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="951dd-118">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="951dd-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="951dd-119">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="951dd-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="951dd-120">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="951dd-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="951dd-121">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="951dd-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="951dd-122">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="951dd-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="951dd-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="951dd-123">Configuration Files</span></span>  

 <span data-ttu-id="951dd-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="951dd-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="951dd-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="951dd-125">Example</span></span>  

 <span data-ttu-id="951dd-126">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase que borra todas las configuraciones de esquema y, a continuación, agrega compatibilidad para no escapar delimitadores de ruta de acceso codificados por porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="951dd-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="951dd-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="951dd-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="951dd-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="951dd-128">Network Settings Schema</span></span>](index.md)
