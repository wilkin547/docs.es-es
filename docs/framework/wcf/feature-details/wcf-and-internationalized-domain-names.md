---
description: 'Más información sobre: WCF y nombres de dominio internacionalizados'
title: WCF y nombres de dominio internacionalizados
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: e7e1ad999d7de749b4f8cf4b3efd823befffba43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755998"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="4662b-103">WCF y nombres de dominio internacionalizados</span><span class="sxs-lookup"><span data-stu-id="4662b-103">WCF and Internationalized Domain Names</span></span>

<span data-ttu-id="4662b-104">Se ha agregado compatibilidad para permitir servicios WCF con nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="4662b-104">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="4662b-105">Un nombre de dominio internacionalizado es un nombre de dominio que contiene caracteres no ASCII.</span><span class="sxs-lookup"><span data-stu-id="4662b-105">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="4662b-106">Esta compatibilidad incluye tanto la capacidad para hospedar un servicio de WCF con un nombre IDN y un cliente de WCF para comunicarse con un servicio web con un nombre IDN.</span><span class="sxs-lookup"><span data-stu-id="4662b-106">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="4662b-107">System.Uri e IDN</span><span class="sxs-lookup"><span data-stu-id="4662b-107">System.Uri and IDN</span></span>  

 <span data-ttu-id="4662b-108"><xref:System.Uri> tiene dos propiedades <xref:System.Uri.Host%2A> y <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="4662b-108"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="4662b-109">Estas propiedades contienen valores Unicode o Punycode dependiendo de las opciones de configuración de IDN.</span><span class="sxs-lookup"><span data-stu-id="4662b-109">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="4662b-110">IDN está habilitada en el archivo de configuración de una aplicación mediante el código XML siguiente</span><span class="sxs-lookup"><span data-stu-id="4662b-110">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="4662b-111">El \<idn> elemento contiene el atributo Enabled que se puede establecer en uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4662b-111">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="4662b-112">"None"</span><span class="sxs-lookup"><span data-stu-id="4662b-112">"None"</span></span>  
  
2. <span data-ttu-id="4662b-113">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="4662b-113">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="4662b-114">"All"</span><span class="sxs-lookup"><span data-stu-id="4662b-114">"All"</span></span>  
  
 <span data-ttu-id="4662b-115">Cuando el valor de IDN se establece en "none", el URI. host o URI. DnsSafeHost no realiza ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="4662b-115">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="4662b-116">Cuando el valor de IDN se establece en "All", Uri. El host sigue siendo Unicode y URI. DnsSafeHost se convierte en Punycode.</span><span class="sxs-lookup"><span data-stu-id="4662b-116">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="4662b-117">Cuando el valor de IDN se establece en "AllExceptIntranet", Uri. DnsSafeHost se convierte en Punycode para direcciones de Internet y sigue siendo Unicode para direcciones de intranet.</span><span class="sxs-lookup"><span data-stu-id="4662b-117">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="4662b-118">Este valor es importante para la resolución de nombres DNS correcta.</span><span class="sxs-lookup"><span data-stu-id="4662b-118">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="4662b-119">Observe que no es necesario configurar este valor para Windows 8 y las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="4662b-119">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="4662b-120">Nunca debe codificar una dirección mediante Punycode.</span><span class="sxs-lookup"><span data-stu-id="4662b-120">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="4662b-121">WCF lo convertirá automáticamente basándose en las opciones de configuración que se apliquen.</span><span class="sxs-lookup"><span data-stu-id="4662b-121">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="4662b-122">Al agregar caracteres Unicode a applicationHost.exe.config, guarde el archivo con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4662b-122">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4662b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4662b-123">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
