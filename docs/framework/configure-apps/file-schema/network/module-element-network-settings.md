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
ms.openlocfilehash: ad641f93e93f627dae1c7d0bda4620093c4567b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205053"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="88709-102">Elemento \<module> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="88709-102">\<module> Element (Network Settings)</span></span>

<span data-ttu-id="88709-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="88709-103">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="88709-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88709-104">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88709-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88709-105">Attributes and Elements</span></span>  

 <span data-ttu-id="88709-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88709-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88709-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="88709-107">Attributes</span></span>  
  
|<span data-ttu-id="88709-108">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="88709-108">**Attribute**</span></span>|<span data-ttu-id="88709-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="88709-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="88709-110">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado por la <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por una coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="88709-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88709-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88709-111">Child Elements</span></span>  

 <span data-ttu-id="88709-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="88709-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88709-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88709-113">Parent Elements</span></span>  
  
|<span data-ttu-id="88709-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="88709-114">**Element**</span></span>|<span data-ttu-id="88709-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="88709-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="88709-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="88709-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="88709-117">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="88709-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88709-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88709-118">Remarks</span></span>  

 <span data-ttu-id="88709-119">El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="88709-119">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="88709-120">Después de registrar la clase de proxy, `module` se puede usar para solicitar información a través del proxy admitido.</span><span class="sxs-lookup"><span data-stu-id="88709-120">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="88709-121">El valor del `type` atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (dll) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="88709-121">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="88709-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="88709-122">Configuration Files</span></span>  

 <span data-ttu-id="88709-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="88709-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88709-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88709-124">Example</span></span>  

 <span data-ttu-id="88709-125">En el ejemplo siguiente se registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="88709-125">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88709-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88709-126">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="88709-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="88709-127">Network Settings Schema</span></span>](index.md)
