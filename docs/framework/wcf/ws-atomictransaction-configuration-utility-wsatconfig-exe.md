---
title: "Utilidad de configuraci&#243;n de WS-AtomicTransaction (wsatConfig.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Utilidad de configuraci&#243;n de WS-AtomicTransaction (wsatConfig.exe)
La utilidad de configuración de WS\-AtomicTransaction se utiliza para configurar valores básicos de compatibilidad de WS\-AtomicTransaction.  
  
## Sintaxis  
  
```  
  
wsatConfig [Options]  
```  
  
## Comentarios  
 Esta herramienta de línea de comandos se puede utilizar para configurar sólo los valores WS\-AT básicos en un equipo local.Si tiene que configurar los valores en los equipos local y remoto, debe utilizar el complemento de MMC, tal y como se describe en [Configuración de la compatibilidad con WS\-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Puede encontrar la herramienta de línea de comandos en la ubicación de instalación de Windows SDK, específicamente  
  
 %SystemRoot%\\Microsoft.Net\\Framework\\v3.0\\Windows Communication Foundation\\wsatConfig.exe  
  
 Si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], debe descargar una actualización antes de ejecutar WsatConfig.exe.Para obtener más información sobre esta actualización, vea [Actualización para Commerce Server 2007 \(KB912817\)](http://go.microsoft.com/fwlink/?LinkId=95340) y [Disponibilidad del Paquete acumulativo de revisión de Windows XP COM\+ 13](http://go.microsoft.com/fwlink/?LinkId=95341).  
  
 La tabla siguiente muestra las opciones que se pueden utilizar con la utilidad de configuración de WS\-AtomicTransaction \(wsatConfig.exe\).  
  
> [!NOTE]
>  Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
|Opciones|Descripción|  
|--------------|-----------------|  
|\-accounts:\<cuenta,\>|Especifica una lista separada por comas de cuentas que pueden participar en WS\-AtomicTransaction.No se comprueba la validez de estas cuentas.|  
|\-accountsCerts:\<control\>&#124;"Issuer\\SubjectName",\>|Especifica una lista separada por comas de certificados que pueden participar en WS\-AtomicTransaction.Los certificados se indican por huella digital o por el par de Issuer\\SubjectName.Utilice {EMPTY} como nombre de sujeto si está vacío.|  
|\-endpointCert:\<equipo&#124;\<control\>&#124;"Issuer\\SubjectName"\>|Utiliza el certificado de equipo u otro certificado del extremo local especificado por huella digital o par de Issuer\\SubjectName.Utiliza {EMPTY} como nombre de sujeto si está vacío.|  
|\-maxTimeout:\<s\>|Especifica el tiempo de espera máximo en segundos.Los valores válidos están comprendidos entre 0 y 3600.|  
|\-network:\<habilitar&#124;deshabilitar\>|Habilita o deshabilita la compatibilidad para red de WS\-AtomicTransaction.|  
|\-port:\<portNum\>|Establece los puertos HTTPS para WS\-AtomicTransaction.<br /><br /> Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones.Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.<br /><br /> Si habilita el firewall después de configurar WS\-AT, tiene que ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro.Si deshabilita el firewall después de configurar, WS\-AT continúa funcionando sin entrada adicional.|  
|\-timeout:\<s\>|Especifica el tiempo de espera predeterminado en segundos.Los valores válidos están comprendidos entre 1 y 3600.|  
|\-traceActivity:\<habilitar&#124;deshabilitar\>|Habilita o deshabilita el seguimiento de eventos de actividad.|  
|\-traceLevel:\<Apagado&#124;Error&#124;Crítico&#124;Advertencia&#124;Información&#124; Detallado&#124;Todos\>}|Especifica el nivel de seguimiento.|  
|\-tracePII:\<habilitar&#124;deshabilitar\>|Habilita o deshabilita el seguimiento de información de identificación personal.|  
|\-traceProp:\<habilitar&#124;deshabilitar\>|Habilita o deshabilita el seguimiento de eventos de propagación.|  
|\-restart|Reinicia MSDTC para activar cambios inmediatamente.Si no se especifica esto, los cambios tienen efecto cuando se reinicia MSDTC.|  
|\-show|Muestra los valores de protocolo actuales de WS\-AtomicTransaction.|  
|\-virtualServer:\<virtualServer\>|Especifica el nombre del clúster de recursos de DTC.|  
  
## Vea también  
 [Utilización de WS\-AtomicTransaction](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)   
 [Configuración de la compatibilidad con WS\-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)