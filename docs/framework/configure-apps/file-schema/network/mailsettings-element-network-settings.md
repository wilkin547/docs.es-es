---
title: Elemento <mailSettings> (configuración de red)
description: El <mailSettings> elemento configuración de red configura las opciones de envío de correo en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: a146874acc21f52507b37b1751c648792e23c8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158856"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="d98ea-103">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d98ea-103">\<mailSettings> Element (Network Settings)</span></span>

<span data-ttu-id="d98ea-104">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="d98ea-104">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="d98ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d98ea-105">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d98ea-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d98ea-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d98ea-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d98ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d98ea-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d98ea-108">Attributes</span></span>  

 <span data-ttu-id="d98ea-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d98ea-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d98ea-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d98ea-110">Child Elements</span></span>  
  
|<span data-ttu-id="d98ea-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d98ea-111">Attribute</span></span>|<span data-ttu-id="d98ea-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d98ea-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d98ea-113">Elemento \<smtp> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d98ea-113">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="d98ea-114">Configura opciones de Protocolo simple de transporte de correo.</span><span class="sxs-lookup"><span data-stu-id="d98ea-114">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d98ea-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d98ea-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d98ea-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="d98ea-116">**Element**</span></span>|<span data-ttu-id="d98ea-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d98ea-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d98ea-118">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d98ea-118">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d98ea-119">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="d98ea-119">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d98ea-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d98ea-120">Example</span></span>  

 <span data-ttu-id="d98ea-121">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d98ea-121">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d98ea-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d98ea-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="d98ea-123">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d98ea-123">Network Settings Schema</span></span>](index.md)
