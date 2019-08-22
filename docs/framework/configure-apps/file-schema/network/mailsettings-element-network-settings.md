---
title: Elemento <mailSettings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: b8ea08cbd76e60a3665703bc50924dd94500cd87
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659329"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="75642-102">\<mailSettings > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="75642-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="75642-103">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="75642-103">Configures mail sending options.</span></span>  

<span data-ttu-id="75642-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75642-104">\<configuration></span></span>  
<span data-ttu-id="75642-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="75642-105">\<system.net></span></span>  
<span data-ttu-id="75642-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="75642-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75642-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75642-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75642-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75642-108">Attributes and Elements</span></span>  
 <span data-ttu-id="75642-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75642-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75642-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="75642-110">Attributes</span></span>  
 <span data-ttu-id="75642-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75642-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75642-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75642-112">Child Elements</span></span>  
  
|<span data-ttu-id="75642-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="75642-113">Attribute</span></span>|<span data-ttu-id="75642-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75642-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="75642-115">\<Elemento > de SMTP (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="75642-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="75642-116">Configura opciones de Protocolo simple de transporte de correo.</span><span class="sxs-lookup"><span data-stu-id="75642-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75642-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75642-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75642-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="75642-118">**Element**</span></span>|<span data-ttu-id="75642-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="75642-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="75642-120">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="75642-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="75642-121">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="75642-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75642-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75642-122">Example</span></span>  
 <span data-ttu-id="75642-123">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="75642-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75642-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="75642-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="75642-125">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="75642-125">Network Settings Schema</span></span>](index.md)
