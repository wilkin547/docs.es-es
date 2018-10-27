---
title: WCF y nombres de dominio internacionalizados
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: a0d4a5b4fe5dd3bc7cf41c8c6ad320dd83861aec
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187928"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="6dfdc-102">WCF y nombres de dominio internacionalizados</span><span class="sxs-lookup"><span data-stu-id="6dfdc-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="6dfdc-103">Se ha agregado compatibilidad para permitir servicios WCF con nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="6dfdc-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="6dfdc-104">Un nombre de dominio internacionalizado es un nombre de dominio que contiene caracteres no ASCII.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="6dfdc-105">Esta compatibilidad incluye tanto la capacidad para hospedar un servicio de WCF con un nombre IDN y un cliente de WCF para comunicarse con un servicio web con un nombre IDN.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="6dfdc-106">System.Uri e IDN</span><span class="sxs-lookup"><span data-stu-id="6dfdc-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="6dfdc-107"><xref:System.Uri> tiene dos propiedades <xref:System.Uri.Host%2A> y <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="6dfdc-108">Estas propiedades contienen valores Unicode o Punycode dependiendo de las opciones de configuración de IDN.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="6dfdc-109">IDN está habilitada en el archivo de configuración de una aplicación mediante el código XML siguiente</span><span class="sxs-lookup"><span data-stu-id="6dfdc-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="6dfdc-110">El \<idn > elemento contiene el atributo enabled que se puede establecer en uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dfdc-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="6dfdc-111">"None"</span><span class="sxs-lookup"><span data-stu-id="6dfdc-111">"None"</span></span>  
  
2.  <span data-ttu-id="6dfdc-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="6dfdc-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="6dfdc-113">"Todo"</span><span class="sxs-lookup"><span data-stu-id="6dfdc-113">"All"</span></span>  
  
 <span data-ttu-id="6dfdc-114">Cuando el valor de IDN se establece en "None", no se realiza ninguna conversión Uri.Host o Uri.DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="6dfdc-115">Cuando el valor de IDN se establece en "All", uri. Host sigue siendo Unicode y uri. DnsSafeHost se convierte en Punycode.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="6dfdc-116">Cuando el valor de IDN se establece en "AllExceptIntranet", el uri. DnsSafeHost se convierte en Punycode para las direcciones de internet y sigue siendo Unicode para las direcciones de intranet.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="6dfdc-117">Este valor es importante para la resolución de nombres DNS correcta.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="6dfdc-118">Observe que no es necesario configurar este valor para Windows 8 y las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6dfdc-119">Nunca debe codificar una dirección mediante Punycode.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="6dfdc-120">WCF lo convertirá automáticamente basándose en las opciones de configuración que se apliquen.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6dfdc-121">Al agregar caracteres Unicode a applicationHost.exe.config, guarde el archivo con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dfdc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dfdc-122">See Also</span></span>  
 <xref:System.Uri?displayProperty=nameWithType>
