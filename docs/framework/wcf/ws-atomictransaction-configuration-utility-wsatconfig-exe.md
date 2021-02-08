---
description: 'Más información acerca de: utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)'
title: Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: 8b315e5aa5df23a4d9bb032db41b7067accfa010
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792965"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)

La utilidad de configuración de WS-AtomicTransaction se utiliza para configurar valores básicos de compatibilidad de WS-AtomicTransaction.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Observaciones

 Esta herramienta de línea de comandos se puede usar para configurar los valores básicos de WS-AT solo en un equipo local. Si tiene que configurar los valores en los equipos locales y remotos, debe usar el complemento MMC como se describe en configuración de la [compatibilidad con transacciones de WS-Atomic](./feature-details/configuring-ws-atomic-transaction-support.md).  
  
 La herramienta de línea de comandos se puede encontrar en la ubicación de instalación de Windows SDK:
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe
  
 La tabla siguiente muestra las opciones que se pueden utilizar con la utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe).  
  
> [!NOTE]
> Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
|Opciones|Descripción|  
|-------------|-----------------|  
|contabilidad\<account,>|Especifica una lista separada por comas de cuentas que pueden participar en WS-AtomicTransaction. No se comprueba la validez de estas cuentas.|  
|-accountsCerts: \<thumb>&#124; "issuer\subjectname.", >|Especifica una lista separada por comas de certificados que pueden participar en WS-AtomicTransaction. Los certificados se indican por huella digital o por el par de Issuer\SubjectName. Utilice {EMPTY} como nombre de sujeto si está vacío.|  
|-endpointCert: <Machine&#124;\<thumb>&#124; "issuer\subjectname." >|Utiliza el certificado de equipo u otro certificado del extremo local especificado por huella digital o par de Issuer\SubjectName. Utiliza {EMPTY} como nombre de sujeto si está vacío.|  
|maxTimeout\<sec>|Especifica el tiempo de espera máximo en segundos. Los valores válidos son de 0 a 3600.|  
|Storage\<enable&#124;disable>|Habilita o deshabilita la compatibilidad para red de WS-AtomicTransaction.|  
|casilla\<portNum>|Establece los puertos HTTPS para WS-AtomicTransaction.<br /><br /> Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones. Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.<br /><br /> Si habilita el firewall después de configurar WS-AT, tiene que ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro. Si deshabilita el firewall después de configurar, WS-AT continúa funcionando sin entrada adicional.|  
|Super\<sec>|Especifica el tiempo de espera predeterminado en segundos. Los valores válidos están comprendidos entre 1 y 3600.|  
|-traceActivity:\<enable&#124;disable>|Habilita o deshabilita el seguimiento de eventos de actividad.|  
|-traceLevel: \<Off&#124;Error&#124;Critical&#124;Warning&#124;Information&#124; Verbose&#124;All> }|Especifica el nivel de seguimiento.|  
|-tracePII:\<enable&#124;disable>|Habilita o deshabilita el seguimiento de información de identificación personal.|  
|-traceProp:\<enable&#124;disable>|Habilita o deshabilita el seguimiento de eventos de propagación.|  
|-restart|Reinicia MSDTC para activar cambios inmediatamente. Si no se especifica esto, los cambios tienen efecto cuando se reinicia MSDTC.|  
|-show|Muestra los valores de protocolo actuales de WS-AtomicTransaction.|  
|servidorVirtual\<virtualServer>|Especifica el nombre del clúster de recursos de DTC.|  
  
## <a name="see-also"></a>Vea también

- [Utilización de WS-AtomicTransaction](./feature-details/using-ws-atomictransaction.md)
- [Configuración de la compatibilidad con WS-Atomic Transaction](./feature-details/configuring-ws-atomic-transaction-support.md)
