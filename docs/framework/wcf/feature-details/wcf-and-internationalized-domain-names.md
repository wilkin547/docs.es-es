---
title: WCF y nombres de dominio internacionalizados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cae287ab440115b15f6c26209a3d40bee4f9703b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF y nombres de dominio internacionalizados
Se ha agregado compatibilidad para permitir servicios WCF con nombres de dominio internacionalizados (IDN). Un nombre de dominio internacionalizado es un nombre de dominio que contiene caracteres no ASCII. Esta compatibilidad incluye tanto la capacidad para hospedar un servicio de WCF con un nombre IDN y un cliente de WCF para comunicarse con un servicio web con un nombre IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri e IDN  
 <xref:System.Uri> tiene dos propiedades <xref:System.Uri.Host%2A> y <xref:System.Uri.DnsSafeHost%2A>. Estas propiedades contienen valores Unicode o Punycode dependiendo de las opciones de configuración de IDN.  
  
 IDN está habilitada en el archivo de configuración de una aplicación mediante el código XML siguiente  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 El \<idn > elemento contiene el atributo enabled que se puede establecer en uno de los siguientes valores:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "All"  
  
 Cuando el valor de IDN se establece en "None", no se realizan conversiones Uri.Host o Uri.DnsSafeHost. Cuando el valor de IDN se establece en "All", uri. Host sigue siendo Unicode y uri. DnsSafeHost se convierte en Punycode. Cuando el valor de IDN se establece en "AllExceptIntranet", el uri. DnsSafeHost se convierte en Punycode para las direcciones de internet y sigue siendo Unicode para las direcciones de intranet. Este valor es importante para la resolución de nombres DNS correcta. Observe que no es necesario configurar este valor para Windows 8 y las versiones más recientes.  
  
> [!WARNING]
>  Nunca debe codificar una dirección mediante Punycode. WCF lo convertirá automáticamente basándose en las opciones de configuración que se apliquen.  
  
> [!WARNING]
>  Al agregar caracteres Unicode a applicationHost.exe.config, guarde el archivo con codificación UTF-8.  
  
## <a name="see-also"></a>Vea también  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)
