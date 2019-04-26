---
title: Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: 30e5a22e54bf977143b2ae94e678ad5106ec9ed6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904493"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)
La utilidad de configuración de WS-AtomicTransaction se utiliza para configurar valores básicos de compatibilidad de WS-AtomicTransaction.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta herramienta de línea de comandos se puede utilizar para configurar sólo los valores WS-AT básicos en un equipo local. Si tiene que establecer la configuración en equipos locales y remotos, debe usar el complemento de MMC como se describe en [configurar WS-Atomic Transaction Support](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Puede encontrar la herramienta de línea de comandos en la ubicación de instalación de Windows SDK, específicamente  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe  
  
 Si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], debe descargar una actualización antes de ejecutar WsatConfig.exe. Para obtener más información sobre esta actualización, consulte [actualización para Commerce Server 2007 (KB912817)](https://go.microsoft.com/fwlink/?LinkId=95340) y [disponibilidad de Windows XP COM + Hotfix Rollup paquete 13](https://go.microsoft.com/fwlink/?LinkId=95341).  
  
 La tabla siguiente muestra las opciones que se pueden utilizar con la utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe).  
  
> [!NOTE]
>  Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
|Opciones|Descripción|  
|-------------|-----------------|  
|-cuentas:\<cuenta >|Especifica una lista separada por comas de cuentas que pueden participar en WS-AtomicTransaction. No se comprueba la validez de estas cuentas.|  
|-accountsCerts:\<thumb >&#124;"Issuer\SubjectName," >|Especifica una lista separada por comas de certificados que pueden participar en WS-AtomicTransaction. Los certificados se indican por huella digital o por el par de Issuer\SubjectName. Utilice {EMPTY} como nombre de sujeto si está vacío.|  
|-endpointCert: < máquina&#124;\<thumb >&#124;"Issuer\SubjectName" >|Utiliza el certificado de equipo u otro certificado del extremo local especificado por huella digital o par de Issuer\SubjectName. Utiliza {EMPTY} como nombre de sujeto si está vacío.|  
|-maxTimeout:\<sec>|Especifica el tiempo de espera máximo en segundos. Los valores válidos van de 0 y 3600.|  
|-red:\<habilitar&#124;deshabilitar >|Habilita o deshabilita la compatibilidad para red de WS-AtomicTransaction.|  
|-puerto:\<portNum >|Establece los puertos HTTPS para WS-AtomicTransaction.<br /><br /> Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones. Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.<br /><br /> Si habilita el firewall después de configurar WS-AT, tiene que ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro. Si deshabilita el firewall después de configurar, WS-AT continúa funcionando sin entrada adicional.|  
|-timeout:\<s >|Especifica el tiempo de espera predeterminado en segundos. Los valores válidos están comprendidos entre 1 y 3600.|  
|-traceActivity:\<habilitar&#124;deshabilitar >|Habilita o deshabilita el seguimiento de eventos de actividad.|  
|-traceLevel:\<desactivar&#124;Error&#124;críticos&#124;advertencia&#124;información&#124; detallado&#124;todos >}|Especifica el nivel de seguimiento.|  
|-tracePII:\<habilitar&#124;deshabilitar >|Habilita o deshabilita el seguimiento de información de identificación personal.|  
|-traceProp:\<habilitar&#124;deshabilitar >|Habilita o deshabilita el seguimiento de eventos de propagación.|  
|-restart|Reinicia MSDTC para activar cambios inmediatamente. Si no se especifica esto, los cambios tienen efecto cuando se reinicia MSDTC.|  
|-show|Muestra los valores de protocolo actuales de WS-AtomicTransaction.|  
|-virtualServer:\<virtualServer>|Especifica el nombre del clúster de recursos de DTC.|  
  
## <a name="see-also"></a>Vea también

- [Utilización de WS-AtomicTransaction](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)
- [Configuración de la compatibilidad con WS-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
