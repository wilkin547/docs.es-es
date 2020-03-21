---
title: Elemento <add> para webRequestModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155029"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="0ce55-102">\<Agregar> Elemento para webRequestModules (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0ce55-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="0ce55-103">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ce55-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="0ce55-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ce55-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0ce55-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0ce55-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0ce55-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0ce55-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="0ce55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="0ce55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0ce55-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ce55-108">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ce55-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ce55-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0ce55-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ce55-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ce55-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ce55-111">Attributes</span></span>  
  
|<span data-ttu-id="0ce55-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="0ce55-112">**Attribute**</span></span>|<span data-ttu-id="0ce55-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0ce55-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="0ce55-114">El prefijo URI para las solicitudes controladas por este módulo de solicitud web.</span><span class="sxs-lookup"><span data-stu-id="0ce55-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="0ce55-115">El nombre de tipo completo <xref:System.Type.FullName%2A> (indicado por la propiedad) y <xref:System.Reflection.Assembly.FullName%2A> el nombre del ensamblado (indicado por la propiedad), separados por una coma, que implementa este módulo de solicitud web.</span><span class="sxs-lookup"><span data-stu-id="0ce55-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ce55-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ce55-116">Child Elements</span></span>  
 <span data-ttu-id="0ce55-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0ce55-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ce55-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ce55-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0ce55-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0ce55-119">**Element**</span></span>|<span data-ttu-id="0ce55-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0ce55-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0ce55-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="0ce55-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="0ce55-122">Especifica los módulos que se utilizarán para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="0ce55-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ce55-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ce55-123">Remarks</span></span>  
 <span data-ttu-id="0ce55-124">El `prefix` atributo define el prefijo URI que utiliza el módulo de solicitud web especificado.</span><span class="sxs-lookup"><span data-stu-id="0ce55-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="0ce55-125">Los módulos de solicitud web se registran normalmente para controlar un protocolo específico, como HTTP o FTP, pero se pueden registrar para controlar una solicitud a un servidor o ruta de acceso específico en un servidor.</span><span class="sxs-lookup"><span data-stu-id="0ce55-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="0ce55-126">El módulo de solicitud web se crea cuando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> se pasa un prefijo de coincidencia de URI al método.</span><span class="sxs-lookup"><span data-stu-id="0ce55-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="0ce55-127">El valor `prefix` del atributo debe ser los caracteres principales de un URI válido.</span><span class="sxs-lookup"><span data-stu-id="0ce55-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="0ce55-128">Por ejemplo, `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="0ce55-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="0ce55-129">El valor `type` del atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="0ce55-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="0ce55-130">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0ce55-130">Configuration Files</span></span>  
 <span data-ttu-id="0ce55-131">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0ce55-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ce55-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ce55-132">Example</span></span>  
 <span data-ttu-id="0ce55-133">En el ejemplo siguiente se registra un módulo de solicitud web personalizado para HTTP.</span><span class="sxs-lookup"><span data-stu-id="0ce55-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="0ce55-134">Debe reemplazar los valores de Version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="0ce55-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ce55-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ce55-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="0ce55-136">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="0ce55-136">Network Settings Schema</span></span>](index.md)
