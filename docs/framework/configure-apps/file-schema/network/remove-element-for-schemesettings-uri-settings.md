---
title: Elemento <remove> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 018a08693a39bb297bdaa468ba59d4bf097f6922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151394"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="1cfff-102">Elemento \<remove> para schemeSettings (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="1cfff-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="1cfff-103">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="1cfff-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="1cfff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cfff-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cfff-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1cfff-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1cfff-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1cfff-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cfff-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1cfff-107">Attributes</span></span>  
  
|<span data-ttu-id="1cfff-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1cfff-108">Attribute</span></span>|<span data-ttu-id="1cfff-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cfff-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cfff-110">name</span><span class="sxs-lookup"><span data-stu-id="1cfff-110">name</span></span>|<span data-ttu-id="1cfff-111">Nombre del esquema para el que se aplica esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1cfff-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="1cfff-112">Los únicos valores admitidos son name = "http" y name = "https".</span><span class="sxs-lookup"><span data-stu-id="1cfff-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cfff-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1cfff-113">Child Elements</span></span>  

 <span data-ttu-id="1cfff-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1cfff-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cfff-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1cfff-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1cfff-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cfff-116">Element</span></span>|<span data-ttu-id="1cfff-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cfff-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cfff-118">\<schemeSettings> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="1cfff-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="1cfff-119">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="1cfff-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cfff-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cfff-120">Remarks</span></span>  

 <span data-ttu-id="1cfff-121">De forma predeterminada, la <xref:System.Uri?displayProperty=nameWithType> clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1cfff-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="1cfff-122">Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cfff-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="1cfff-123">Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1cfff-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="1cfff-124">Por esta razón, la <xref:System.Uri?displayProperty=nameWithType> clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1cfff-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="1cfff-125">El resultado de pasar la dirección URL malintencionada anterior al <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="1cfff-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="1cfff-126">Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="1cfff-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1cfff-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1cfff-127">Configuration Files</span></span>  

 <span data-ttu-id="1cfff-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1cfff-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cfff-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cfff-129">Example</span></span>  

 <span data-ttu-id="1cfff-130">En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase que quita cualquier configuración de esquema para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="1cfff-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cfff-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cfff-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="1cfff-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1cfff-132">Network Settings Schema</span></span>](index.md)
