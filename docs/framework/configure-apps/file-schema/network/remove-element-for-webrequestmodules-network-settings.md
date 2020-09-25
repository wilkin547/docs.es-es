---
title: Elemento <remove> para webRequestModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 65e8b1f2088015b86d4f981f07875d236a11a617
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176193"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="1abaf-102">Elemento \<remove> para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1abaf-102">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="1abaf-103">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1abaf-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="1abaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1abaf-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1abaf-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1abaf-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1abaf-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1abaf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1abaf-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1abaf-107">Attributes</span></span>  
  
|<span data-ttu-id="1abaf-108">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="1abaf-108">**Attribute**</span></span>|<span data-ttu-id="1abaf-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1abaf-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="1abaf-110">El prefijo URI para las solicitudes controladas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="1abaf-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1abaf-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1abaf-111">Child Elements</span></span>  

 <span data-ttu-id="1abaf-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1abaf-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1abaf-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1abaf-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1abaf-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="1abaf-114">**Element**</span></span>|<span data-ttu-id="1abaf-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1abaf-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1abaf-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="1abaf-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="1abaf-117">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="1abaf-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1abaf-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1abaf-118">Remarks</span></span>  

 <span data-ttu-id="1abaf-119">El `remove` elemento quita el módulo de solicitud Web registrado para el prefijo de URI especificado.</span><span class="sxs-lookup"><span data-stu-id="1abaf-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="1abaf-120">El valor del `prefix` atributo debe ser el carácter inicial de un URI válido (por ejemplo, " `http` " o " `http://www.contoso.com` ").</span><span class="sxs-lookup"><span data-stu-id="1abaf-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1abaf-121">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1abaf-121">Configuration Files</span></span>  

 <span data-ttu-id="1abaf-122">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1abaf-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1abaf-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1abaf-123">Example</span></span>  

<span data-ttu-id="1abaf-124">En el ejemplo siguiente se quita el módulo de solicitud Web existente para HTTP y, después, se registra un nuevo módulo de solicitud web personalizado para las solicitudes HTTP a `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1abaf-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1abaf-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1abaf-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="1abaf-126">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1abaf-126">Network Settings Schema</span></span>](index.md)
