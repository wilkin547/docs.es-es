---
title: Elemento <defaultProxy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698210"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="a5308-102">\<elemento > defaultProxy (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a5308-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="a5308-103">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="a5308-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[<span data-ttu-id="a5308-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a5308-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a5308-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a5308-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="a5308-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultProxy >**</span><span class="sxs-lookup"><span data-stu-id="a5308-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5308-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5308-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5308-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5308-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a5308-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5308-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5308-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5308-110">Attributes</span></span>  
  
|<span data-ttu-id="a5308-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="a5308-111">**Element**</span></span>|<span data-ttu-id="a5308-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5308-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="a5308-113">Especifica si se usa un proxy web.</span><span class="sxs-lookup"><span data-stu-id="a5308-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="a5308-114">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a5308-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="a5308-115">Especifica si se usan las credenciales predeterminadas de este host para tener acceso al proxy web.</span><span class="sxs-lookup"><span data-stu-id="a5308-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="a5308-116">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a5308-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5308-117">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="a5308-117">Child Elements</span></span>  
  
|<span data-ttu-id="a5308-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="a5308-118">**Element**</span></span>|<span data-ttu-id="a5308-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5308-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a5308-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="a5308-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="a5308-121">Proporciona un conjunto de expresiones regulares que describen direcciones que no usan el proxy.</span><span class="sxs-lookup"><span data-stu-id="a5308-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="a5308-122">module</span><span class="sxs-lookup"><span data-stu-id="a5308-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="a5308-123">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5308-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="a5308-124">proxi</span><span class="sxs-lookup"><span data-stu-id="a5308-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="a5308-125">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="a5308-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5308-126">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="a5308-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a5308-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="a5308-127">**Element**</span></span>|<span data-ttu-id="a5308-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5308-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a5308-129">system.net</span><span class="sxs-lookup"><span data-stu-id="a5308-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a5308-130">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="a5308-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5308-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5308-131">Remarks</span></span>  
 <span data-ttu-id="a5308-132">Si el elemento defaultProxy está vacío, se usará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a5308-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="a5308-133">Este comportamiento es diferente de la versión 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5308-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a5308-134">Se produce una excepción si el elemento [Module](module-element-network-settings.md) especifica un tipo no público, el tipo no se deriva de la clase <xref:System.Net.IWebProxy>, se produjo una excepción del constructor sin parámetros de este objeto o se produjo una excepción al recuperar el proxy predeterminado especificado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="a5308-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="a5308-135">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.</span><span class="sxs-lookup"><span data-stu-id="a5308-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a5308-136">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5308-136">Configuration Files</span></span>  
 <span data-ttu-id="a5308-137">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a5308-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5308-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5308-138">Example</span></span>  
 <span data-ttu-id="a5308-139">En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local y contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a5308-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5308-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5308-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a5308-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a5308-141">Network Settings Schema</span></span>](index.md)
