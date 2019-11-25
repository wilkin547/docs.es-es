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
ms.openlocfilehash: 76dad0c0b75d20627e9f57fd1bb467bf17c9294c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088512"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="856c1-102">\<agregar > elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="856c1-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="856c1-103">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="856c1-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="856c1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="856c1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="856c1-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="856c1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="856c1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules**](webrequestmodules-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="856c1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="856c1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="856c1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="856c1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="856c1-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="856c1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="856c1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="856c1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="856c1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="856c1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="856c1-111">Attributes</span></span>  
  
|<span data-ttu-id="856c1-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="856c1-112">**Attribute**</span></span>|<span data-ttu-id="856c1-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="856c1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="856c1-114">El prefijo URI para las solicitudes controladas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="856c1-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="856c1-115">El nombre de tipo completo (indicado por la propiedad <xref:System.Type.FullName%2A>) y el nombre del ensamblado (indicado por la propiedad <xref:System.Reflection.Assembly.FullName%2A>), separados por una coma, que implementa este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="856c1-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="856c1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="856c1-116">Child Elements</span></span>  
 <span data-ttu-id="856c1-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="856c1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="856c1-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="856c1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="856c1-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="856c1-119">**Element**</span></span>|<span data-ttu-id="856c1-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="856c1-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="856c1-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="856c1-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="856c1-122">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="856c1-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="856c1-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="856c1-123">Remarks</span></span>  
 <span data-ttu-id="856c1-124">El atributo `prefix` define el prefijo URI que utiliza el módulo de solicitud Web especificado.</span><span class="sxs-lookup"><span data-stu-id="856c1-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="856c1-125">Los módulos de solicitud Web normalmente se registran para controlar un protocolo específico, como HTTP o FTP, pero se pueden registrar para controlar una solicitud a un servidor o ruta de acceso específicos en un servidor.</span><span class="sxs-lookup"><span data-stu-id="856c1-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="856c1-126">El módulo de solicitud Web se crea cuando se pasa un prefijo coincidente de URI al método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="856c1-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="856c1-127">El valor del atributo `prefix` debe ser el carácter inicial de un URI válido.</span><span class="sxs-lookup"><span data-stu-id="856c1-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="856c1-128">Por ejemplo: `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="856c1-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="856c1-129">El valor del atributo `type` debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="856c1-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="856c1-130">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="856c1-130">Configuration Files</span></span>  
 <span data-ttu-id="856c1-131">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="856c1-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="856c1-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="856c1-132">Example</span></span>  
 <span data-ttu-id="856c1-133">En el ejemplo siguiente se registra un módulo de solicitud web personalizado para HTTP.</span><span class="sxs-lookup"><span data-stu-id="856c1-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="856c1-134">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="856c1-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="856c1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="856c1-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="856c1-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="856c1-136">Network Settings Schema</span></span>](index.md)
