---
description: 'Más información sobre: <add> elemento para webRequestModules (configuración de red)'
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
ms.openlocfilehash: 1edb63a1e1095bb4b3c3d749fd389ffaad5ddf9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729900"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="b316e-103">Elemento \<add> para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="b316e-103">\<add> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="b316e-104">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b316e-104">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="b316e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b316e-105">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b316e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b316e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b316e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b316e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b316e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b316e-108">Attributes</span></span>  
  
|<span data-ttu-id="b316e-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="b316e-109">**Attribute**</span></span>|<span data-ttu-id="b316e-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b316e-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="b316e-111">El prefijo URI para las solicitudes controladas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="b316e-111">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="b316e-112">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado por la <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por una coma, que implementa este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="b316e-112">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b316e-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b316e-113">Child Elements</span></span>  

 <span data-ttu-id="b316e-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b316e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b316e-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b316e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b316e-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="b316e-116">**Element**</span></span>|<span data-ttu-id="b316e-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b316e-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b316e-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="b316e-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="b316e-119">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="b316e-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b316e-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b316e-120">Remarks</span></span>  

 <span data-ttu-id="b316e-121">El `prefix` atributo define el prefijo URI que utiliza el módulo de solicitud Web especificado.</span><span class="sxs-lookup"><span data-stu-id="b316e-121">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="b316e-122">Los módulos de solicitud Web normalmente se registran para controlar un protocolo específico, como HTTP o FTP, pero se pueden registrar para controlar una solicitud a un servidor o ruta de acceso específicos en un servidor.</span><span class="sxs-lookup"><span data-stu-id="b316e-122">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="b316e-123">El módulo de solicitud Web se crea cuando se pasa al método un prefijo coincidente con el URI <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b316e-123">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b316e-124">El valor del `prefix` atributo debe ser el carácter inicial de un URI válido.</span><span class="sxs-lookup"><span data-stu-id="b316e-124">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="b316e-125">Por ejemplo, `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="b316e-125">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="b316e-126">El valor del `type` atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="b316e-126">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="b316e-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b316e-127">Configuration Files</span></span>  

 <span data-ttu-id="b316e-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b316e-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b316e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b316e-129">Example</span></span>  

 <span data-ttu-id="b316e-130">En el ejemplo siguiente se registra un módulo de solicitud web personalizado para HTTP.</span><span class="sxs-lookup"><span data-stu-id="b316e-130">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="b316e-131">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="b316e-131">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b316e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b316e-132">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="b316e-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="b316e-133">Network Settings Schema</span></span>](index.md)
