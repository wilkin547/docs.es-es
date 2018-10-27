---
title: '&lt;módulo&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 2d263fd64475d119d536e7cef69896fcfa5ae42c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183703"
---
# <a name="ltmodulegt-element-network-settings"></a><span data-ttu-id="1c5f8-102">&lt;módulo&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1c5f8-102">&lt;module&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1c5f8-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="1c5f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c5f8-104">\<configuration></span></span>  
<span data-ttu-id="1c5f8-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="1c5f8-105">\<system.net></span></span>  
<span data-ttu-id="1c5f8-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="1c5f8-106">\<defaultProxy></span></span>  
<span data-ttu-id="1c5f8-107">\<módulo ></span><span class="sxs-lookup"><span data-stu-id="1c5f8-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5f8-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c5f8-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c5f8-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c5f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c5f8-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c5f8-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c5f8-111">Attributes</span></span>  
  
|<span data-ttu-id="1c5f8-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="1c5f8-112">**Attribute**</span></span>|<span data-ttu-id="1c5f8-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1c5f8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="1c5f8-114">El nombre de tipo completo (indicado por el <xref:System.Type.FullName%2A> propiedad) y el nombre del ensamblado (indicado por el <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por punto y coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c5f8-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c5f8-115">Child Elements</span></span>  
 <span data-ttu-id="1c5f8-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c5f8-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c5f8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1c5f8-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="1c5f8-118">**Element**</span></span>|<span data-ttu-id="1c5f8-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1c5f8-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c5f8-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="1c5f8-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="1c5f8-121">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="1c5f8-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c5f8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c5f8-122">Remarks</span></span>  
 <span data-ttu-id="1c5f8-123">El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="1c5f8-124">Después de registrar la clase de proxy, `module` se puede usar para solicitar información a través del proxy compatible.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="1c5f8-125">El valor de la `type` atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (DLL) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1c5f8-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1c5f8-126">Configuration Files</span></span>  
 <span data-ttu-id="1c5f8-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1c5f8-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c5f8-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c5f8-128">Example</span></span>  
 <span data-ttu-id="1c5f8-129">El ejemplo siguiente registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="1c5f8-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c5f8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c5f8-130">See Also</span></span>  
- <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
- [<span data-ttu-id="1c5f8-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1c5f8-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
