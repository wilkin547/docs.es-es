---
description: 'Más información sobre: <remove> elemento para BypassList (configuración de red)'
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
ms.openlocfilehash: 48441f1b402b339a1bd2ea069678afb4b1d5f2e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740293"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="651f8-103">Elemento \<remove> para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="651f8-103">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="651f8-104">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="651f8-104">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="651f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="651f8-105">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="651f8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="651f8-106">Attributes and Elements</span></span>

<span data-ttu-id="651f8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="651f8-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="651f8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="651f8-108">Attributes</span></span>

|<span data-ttu-id="651f8-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="651f8-109">**Attribute**</span></span>|<span data-ttu-id="651f8-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="651f8-110">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="651f8-111">Expresión regular que describe una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="651f8-111">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="651f8-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="651f8-112">Child Elements</span></span>

<span data-ttu-id="651f8-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="651f8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="651f8-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="651f8-114">Parent Elements</span></span>

|<span data-ttu-id="651f8-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="651f8-115">**Element**</span></span>|<span data-ttu-id="651f8-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="651f8-116">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="651f8-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="651f8-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="651f8-118">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="651f8-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="651f8-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="651f8-119">Remarks</span></span>

<span data-ttu-id="651f8-120">El `remove` elemento quita las expresiones regulares que describen las direcciones IP o los nombres de servidor DNS de la lista de direcciones que omiten un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="651f8-120">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="651f8-121">Las direcciones se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="651f8-121">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="651f8-122">El valor del `address` atributo debe ser una expresión regular que describa un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="651f8-122">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="651f8-123">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="651f8-123">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="651f8-124">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="651f8-124">Configuration Files</span></span>

<span data-ttu-id="651f8-125">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="651f8-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="651f8-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="651f8-126">Example</span></span>

<span data-ttu-id="651f8-127">En el ejemplo siguiente se quita cualquier definición anterior del dominio adventure-works.com y, a continuación, se agrega el dominio contoso.com a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="651f8-127">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="651f8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="651f8-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="651f8-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="651f8-129">Network Settings Schema</span></span>](index.md)
