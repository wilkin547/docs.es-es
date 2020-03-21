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
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154834"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="d83fc-102">\<elemento> módulo (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d83fc-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="d83fc-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d83fc-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="d83fc-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d83fc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d83fc-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d83fc-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d83fc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d83fc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="d83fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<módulo>**</span><span class="sxs-lookup"><span data-stu-id="d83fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d83fc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d83fc-108">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d83fc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d83fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d83fc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d83fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d83fc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d83fc-111">Attributes</span></span>  
  
|<span data-ttu-id="d83fc-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="d83fc-112">**Attribute**</span></span>|<span data-ttu-id="d83fc-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d83fc-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="d83fc-114">El nombre de tipo completo <xref:System.Type.FullName%2A> (indicado por la propiedad) y <xref:System.Reflection.Assembly.FullName%2A> el nombre del ensamblado (indicado por la propiedad), separados por una coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="d83fc-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d83fc-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d83fc-115">Child Elements</span></span>  
 <span data-ttu-id="d83fc-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d83fc-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d83fc-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d83fc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d83fc-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d83fc-118">**Element**</span></span>|<span data-ttu-id="d83fc-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d83fc-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d83fc-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="d83fc-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="d83fc-121">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="d83fc-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d83fc-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d83fc-122">Remarks</span></span>  
 <span data-ttu-id="d83fc-123">El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="d83fc-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="d83fc-124">Después de registrar `module` la clase de proxy, se puede utilizar para solicitar información a través del proxy admitido.</span><span class="sxs-lookup"><span data-stu-id="d83fc-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="d83fc-125">El valor `type` del atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (DLL) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d83fc-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d83fc-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d83fc-126">Configuration Files</span></span>  
 <span data-ttu-id="d83fc-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d83fc-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d83fc-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d83fc-128">Example</span></span>  
 <span data-ttu-id="d83fc-129">En el ejemplo siguiente se registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="d83fc-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d83fc-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d83fc-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="d83fc-131">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="d83fc-131">Network Settings Schema</span></span>](index.md)
