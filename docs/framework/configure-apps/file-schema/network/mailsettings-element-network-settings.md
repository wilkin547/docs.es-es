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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089231"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="3aa80-102">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3aa80-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="3aa80-103">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="3aa80-103">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="3aa80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3aa80-104">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3aa80-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3aa80-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3aa80-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3aa80-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3aa80-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3aa80-107">Attributes</span></span>  
 <span data-ttu-id="3aa80-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3aa80-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3aa80-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3aa80-109">Child Elements</span></span>  
  
|<span data-ttu-id="3aa80-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="3aa80-110">Attribute</span></span>|<span data-ttu-id="3aa80-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3aa80-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3aa80-112">\<smtp>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3aa80-112">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="3aa80-113">Configura opciones de Protocolo simple de transporte de correo.</span><span class="sxs-lookup"><span data-stu-id="3aa80-113">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3aa80-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3aa80-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3aa80-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="3aa80-115">**Element**</span></span>|<span data-ttu-id="3aa80-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3aa80-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3aa80-117">\<system.Net>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3aa80-117">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="3aa80-118">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="3aa80-118">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3aa80-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3aa80-119">Example</span></span>  
 <span data-ttu-id="3aa80-120">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3aa80-120">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3aa80-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3aa80-121">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="3aa80-122">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="3aa80-122">Network Settings Schema</span></span>](index.md)
