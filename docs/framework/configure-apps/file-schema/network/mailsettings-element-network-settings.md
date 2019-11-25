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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089231"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="a147f-102">\<elemento > mailSettings (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a147f-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="a147f-103">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="a147f-103">Configures mail sending options.</span></span>  

<span data-ttu-id="a147f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a147f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a147f-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a147f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="a147f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<mailSettings >**</span><span class="sxs-lookup"><span data-stu-id="a147f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a147f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a147f-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a147f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a147f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a147f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a147f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a147f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a147f-110">Attributes</span></span>  
 <span data-ttu-id="a147f-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a147f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a147f-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a147f-112">Child Elements</span></span>  
  
|<span data-ttu-id="a147f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a147f-113">Attribute</span></span>|<span data-ttu-id="a147f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a147f-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a147f-115">\<elemento > de SMTP (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a147f-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="a147f-116">Configura opciones de Protocolo simple de transporte de correo.</span><span class="sxs-lookup"><span data-stu-id="a147f-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a147f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a147f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a147f-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="a147f-118">**Element**</span></span>|<span data-ttu-id="a147f-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a147f-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a147f-120">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a147f-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a147f-121">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="a147f-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a147f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a147f-122">Example</span></span>  
 <span data-ttu-id="a147f-123">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="a147f-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a147f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a147f-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="a147f-125">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a147f-125">Network Settings Schema</span></span>](index.md)
