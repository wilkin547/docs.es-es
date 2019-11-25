---
title: Elemento <module> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 78f6418160b80096214c6e37268a5a90498d6d4d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089241"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="33e01-102">\<el elemento > del módulo (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="33e01-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="33e01-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33e01-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="33e01-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33e01-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33e01-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="33e01-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="33e01-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="33e01-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="33e01-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**módulo** ></span><span class="sxs-lookup"><span data-stu-id="33e01-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="33e01-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33e01-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33e01-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33e01-109">Attributes and Elements</span></span>  
 <span data-ttu-id="33e01-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33e01-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33e01-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="33e01-111">Attributes</span></span>  
  
|<span data-ttu-id="33e01-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="33e01-112">**Attribute**</span></span>|<span data-ttu-id="33e01-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="33e01-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="33e01-114">El nombre de tipo completo (indicado por la propiedad <xref:System.Type.FullName%2A>) y el nombre del ensamblado (indicado por la propiedad <xref:System.Reflection.Assembly.FullName%2A>), separados por una coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="33e01-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33e01-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33e01-115">Child Elements</span></span>  
 <span data-ttu-id="33e01-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33e01-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33e01-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33e01-117">Parent Elements</span></span>  
  
|<span data-ttu-id="33e01-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="33e01-118">**Element**</span></span>|<span data-ttu-id="33e01-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="33e01-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="33e01-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="33e01-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="33e01-121">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="33e01-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33e01-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33e01-122">Remarks</span></span>  
 <span data-ttu-id="33e01-123">El elemento `module` registra las clases de proxy que implementan la interfaz <xref:System.Net.IWebProxy>.</span><span class="sxs-lookup"><span data-stu-id="33e01-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="33e01-124">Después de registrar la clase de proxy, `module` se puede usar para solicitar información a través del proxy admitido.</span><span class="sxs-lookup"><span data-stu-id="33e01-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="33e01-125">El valor del atributo `type` debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (DLL) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="33e01-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="33e01-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="33e01-126">Configuration Files</span></span>  
 <span data-ttu-id="33e01-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="33e01-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33e01-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33e01-128">Example</span></span>  
 <span data-ttu-id="33e01-129">En el ejemplo siguiente se registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="33e01-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33e01-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="33e01-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="33e01-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="33e01-131">Network Settings Schema</span></span>](index.md)
