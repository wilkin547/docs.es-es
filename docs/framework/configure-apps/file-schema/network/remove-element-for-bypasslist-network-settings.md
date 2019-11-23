---
title: Elemento <remove> para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697891"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="d9a9c-102">\<quitar > elemento para BypassList (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d9a9c-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="d9a9c-103">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[<span data-ttu-id="d9a9c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d9a9c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d9a9c-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d9a9c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d9a9c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d9a9c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="d9a9c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BypassList >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d9a9c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="d9a9c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**quitar >**</span><span class="sxs-lookup"><span data-stu-id="d9a9c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d9a9c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a9c-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9a9c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9a9c-110">Attributes and Elements</span></span>

<span data-ttu-id="d9a9c-111">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9a9c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9a9c-112">Attributes</span></span>

|<span data-ttu-id="d9a9c-113">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="d9a9c-113">**Attribute**</span></span>|<span data-ttu-id="d9a9c-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9a9c-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="d9a9c-115">Expresión regular que describe una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d9a9c-116">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="d9a9c-116">Child Elements</span></span>

<span data-ttu-id="d9a9c-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d9a9c-118">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="d9a9c-118">Parent Elements</span></span>

|<span data-ttu-id="d9a9c-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="d9a9c-119">**Element**</span></span>|<span data-ttu-id="d9a9c-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9a9c-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="d9a9c-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="d9a9c-121">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="d9a9c-122">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9a9c-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9a9c-123">Remarks</span></span>

<span data-ttu-id="d9a9c-124">El elemento `remove` quita las expresiones regulares que describen las direcciones IP o los nombres de servidor DNS de la lista de direcciones que omiten un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="d9a9c-125">Las direcciones se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="d9a9c-126">El valor del atributo `address` debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="d9a9c-127">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d9a9c-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="d9a9c-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d9a9c-128">Configuration Files</span></span>

<span data-ttu-id="d9a9c-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d9a9c-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="d9a9c-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9a9c-130">Example</span></span>

<span data-ttu-id="d9a9c-131">En el ejemplo siguiente se quita cualquier definición anterior del dominio adventure-works.com y, a continuación, se agrega el dominio contoso.com a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="d9a9c-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d9a9c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a9c-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="d9a9c-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d9a9c-133">Network Settings Schema</span></span>](index.md)
