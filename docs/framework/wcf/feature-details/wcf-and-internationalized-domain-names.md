---
title: WCF y nombres de dominio internacionalizados
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 2d93bbb0c284c2227a4d03acf1ad9a801df57bd8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281994"
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
  
 El \<idn> elemento contiene el atributo Enabled que se puede establecer en uno de los valores siguientes:  
  
1. "None"  
  
2. "AllExceptIntranet"  
  
3. "All"  
  
 Cuando el valor de IDN se establece en "none", el URI. host o URI. DnsSafeHost no realiza ninguna conversión. Cuando el valor de IDN se establece en "All", Uri. El host sigue siendo Unicode y URI. DnsSafeHost se convierte en Punycode. Cuando el valor de IDN se establece en "AllExceptIntranet", Uri. DnsSafeHost se convierte en Punycode para direcciones de Internet y sigue siendo Unicode para direcciones de intranet. Este valor es importante para la resolución de nombres DNS correcta. Observe que no es necesario configurar este valor para Windows 8 y las versiones más recientes.  
  
> [!WARNING]
> Nunca debe codificar una dirección mediante Punycode. WCF lo convertirá automáticamente basándose en las opciones de configuración que se apliquen.  
  
> [!WARNING]
> Al agregar caracteres Unicode a applicationHost.exe.config, guarde el archivo con codificación UTF-8.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Uri?displayProperty=nameWithType>
