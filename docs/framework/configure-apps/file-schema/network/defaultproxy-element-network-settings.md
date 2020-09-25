---
title: Elemento <defaultProxy> (configuración de red)
description: El <defaultProxy> elemento de configuración de red configura el servidor proxy del Protocolo de transferencia de hipertexto (http) en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 806a30a52219ef9185f84a650d6a8eef8fb0dc8c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190311"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="d8cf8-103">Elemento \<defaultProxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d8cf8-103">\<defaultProxy> Element (Network Settings)</span></span>

<span data-ttu-id="d8cf8-104">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="d8cf8-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="d8cf8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8cf8-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="True|False"  
  useDefaultCredentials="True|False">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8cf8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d8cf8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d8cf8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8cf8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8cf8-108">Attributes</span></span>  
  
|<span data-ttu-id="d8cf8-109">**Element**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-109">**Element**</span></span>|<span data-ttu-id="d8cf8-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="d8cf8-111">Especifica si se usa un proxy web.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="d8cf8-112">El valor predeterminado es `True`.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-112">The default value is `True`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="d8cf8-113">Especifica si se usan las credenciales predeterminadas de este host para tener acceso al proxy web.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="d8cf8-114">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-114">The default value is `False`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8cf8-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d8cf8-115">Child Elements</span></span>  
  
|<span data-ttu-id="d8cf8-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-116">**Element**</span></span>|<span data-ttu-id="d8cf8-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8cf8-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="d8cf8-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="d8cf8-119">Proporciona un conjunto de expresiones regulares que describen direcciones que no usan el proxy.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="d8cf8-120">destina</span><span class="sxs-lookup"><span data-stu-id="d8cf8-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="d8cf8-121">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="d8cf8-122">proxi</span><span class="sxs-lookup"><span data-stu-id="d8cf8-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="d8cf8-123">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8cf8-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d8cf8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d8cf8-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-125">**Element**</span></span>|<span data-ttu-id="d8cf8-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8cf8-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8cf8-127">system.net</span><span class="sxs-lookup"><span data-stu-id="d8cf8-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d8cf8-128">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8cf8-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8cf8-129">Remarks</span></span>  

 <span data-ttu-id="d8cf8-130">Si el elemento defaultProxy está vacío, se usará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="d8cf8-131">Este comportamiento es diferente de la versión 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d8cf8-132">Se produce una excepción si el elemento [Module](module-element-network-settings.md) especifica un tipo no público, el tipo no se deriva de la <xref:System.Net.IWebProxy> clase, se produjo una excepción del constructor sin parámetros de este objeto o se produjo una excepción al recuperar el proxy predeterminado especificado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="d8cf8-133">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d8cf8-134">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d8cf8-134">Configuration Files</span></span>  

 <span data-ttu-id="d8cf8-135">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d8cf8-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8cf8-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8cf8-136">Example</span></span>  

 <span data-ttu-id="d8cf8-137">En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local y contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d8cf8-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8cf8-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8cf8-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="d8cf8-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d8cf8-139">Network Settings Schema</span></span>](index.md)
