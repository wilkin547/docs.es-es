---
title: "Complemento MMC de configuraci&#243;n de WS-AtomicTransaction | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Complemento MMC de configuraci&#243;n de WS-AtomicTransaction
El complemento MMC de configuración de WS\-AtomicTransaction se utiliza para configurar una parte de los valores WS\-AtomicTransaction en los equipos local remoto.  
  
## Notas  
 Si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], puede encontrar el complemento MMC navegando a **Panel de control\/Herramientas administrativas\/Servicios de componentes**, haciendo clic con el botón secundario en **Mi PC**, y seleccionando **Propiedades**.Ésta es la misma ubicación donde puede configurar MSDTC.Las opciones de configuración disponibles están agrupadas en la pestaña **WS\-AT**.  
  
 Si está ejecutando Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], puede encontrar el complemento MMC haciendo clic en el botón **Inicio** y escribiendo `dcomcnfg.exe` en el cuadro **Buscar**.Cuando se abra MMC, navegue al nodo **Mi PC\\Coordinador de transacciones distribuidas\\DTC local**, haga clic con el botón secundario del ratón y seleccione **Propiedades**.Las opciones de configuración disponibles están agrupadas en la pestaña **WS\-AT**.  
  
 Los pasos anteriores se utilizan para iniciar el complemento para configurar un equipo local.Si desea configurar un equipo remoto, debe buscar el nombre del equipo remoto en **Panel de control\/Herramientas administrativas\/Servicios de componentes\/**y realizar los mismos pasos si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)].Si está ejecutando Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], siga los pasos anteriores para Vista y [!INCLUDE[lserver](../../../includes/lserver-md.md)], pero utilice **Coordinador de transacciones distribuidas\\DTC local** bajo el nodo del equipo remoto.  
  
 Para utilizar la interfaz de usuario proporcionada por la herramienta, tiene que registrar el archivo WsatUI.dll, que se encuentra en la ruta de acceso siguiente  
  
 **%PROGRAMFILES%\\Microsoft SDKs\\Windows\\v6.0\\Bin\\WsatUI.dll**  
  
 El comando siguiente puede hacer el registro.  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 Puede utilizar esta herramienta para modificar los valores básicos de WS\-AtomicTransaction.Por ejemplo, puede habilitar y deshabilitar la compatibilidad de protocolo de WS\-AtomicTransaction, configurar los puertos del HTTP para WS\-AT, enlazar un Certificado SSL al puerto HTTP, configurar los certificados especificando los nombres de sujeto de certificado, seleccionar el modo de seguimiento y establecer los tiempos de espera predeterminado y máximo.  
  
 Si debe configurar la compatibilidad de WS\-AtomicTransaction solo en el equipo local, puede usar la versión de línea de comandos de esta herramienta.[!INCLUDE[crabout](../../../includes/crabout-md.md)] la herramienta de línea de comandos, vea el tema [Utilidad de configuración de WS\-AtomicTransaction \(wsatConfig.exe\)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).  
  
 Debe tener en cuenta que tanto el complemento MMC como la herramienta de la línea de comandos no permiten configurar todos los valores WS\-AT.Esta configuración sólo se puede editar modificando directamente el registro.[!INCLUDE[crabout](../../../includes/crabout-md.md)] estos valores del Registro, vea [Configuración de la compatibilidad con WS\-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### Descripción de la interfaz de usuario  
 **Habilitar Compatibilidad para red de WS\-Atomic Transaction**:  
  
 Esta casilla habilita o deshabilita todos los componentes GUI de este complemento.  
  
 Antes de marcar la casilla, debería asegurarse de que el acceso DTC a red está habilitado con comunicación entrante o saliente, o ambas.Este valor se puede comprobar en la pestaña **Seguridad** del complemento MSDTC.  
  
#### Cuadro Grupo de red  
 Puede especificar el puerto HTTPS y configuración de seguridad adicional como cifrado SSL en el grupo de red.Este grupo está deshabilitado \(atenuado\) si no están habilitadas las transacciones de red DTC.  
  
 **Puerto HTTPS**  
  
 Éste es el valor del puerto HTTPS utilizado para WS\-AT.El valor debe ser un número en el intervalo 1\-65535 \(para representar un puerto válido\).Al cambiar el puerto HTTP se modifica la configuración de servicio HTTP, lo que significa que se libera la dirección de servicio WS\-AT previamente utilizada y se registra una dirección de servicio WS\-AT nueva basado del nuevo puerto.Además, el puerto recientemente seleccionado se cifra con el certificado seleccionado actualmente para cifrado SSL.  
  
> [!NOTE]
>  Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones.Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.  
  
 Si habilita el firewall después de configurar WS\-AT, debe ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro.Si deshabilita el firewall después de configurar, WS\-AT continúa funcionando sin entrada adicional.  
  
 **Certificado de extremo**  
  
 Al hacer clic en el botón **Seleccionar**, se muestra una lista con los certificados actualmente disponibles en el equipo local y se permite que el usuario seleccione el certificado que se puede utilizar para el cifrado SSL.Los certificados tienen que tener una clave privada.De lo contrario, recibirá un mensaje de error.  
  
> [!NOTE]
>  Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
 **Cuentas autorizadas**  
  
 Al hacer clic en el botón **Seleccionar**, se invoca el editor de lista de control de acceso de Windows, donde puede especificar al usuario o el grupo que puede participar en WS\-Atomic Transactions marcando la casilla **Permitir** o **Denegar** en el grupo de permiso **Participar**.  
  
 **Certificados autorizados**  
  
 Al hacer clic en el botón **Seleccionar**, se muestra una lista de certificados actualmente disponibles en el equipo local.Puede seleccionar a continuación qué identidades del certificado pueden participar en WS\-Atomic Transactions.  
  
#### Cuadro de grupo Tiempo de espera  
 El cuadro de grupo **Tiempo de espera** le permite especificar el tiempo de espera predeterminado y máximo para una transacción de WS\-Atomic.Un valor válido para el tiempo de espera de salida está entre 1 y 3600.Un valor válido para el tiempo de espera de entrada está entre 0 y 3600.  
  
#### Cuadro de grupo Seguimiento y registro  
 El cuadro de grupo **Seguimiento y registro** le permite configurar el nivel de seguimiento y registro deseado.  
  
 Al hacer clic en el botón **Opciones**, se invoca una página donde puede especificar los valores adicionales.  
  
 El cuadro combinado **Nivel de seguimiento** le permite elegir cualquier valor válido de la enumeración <xref:System.Diagnostics.TraceLevel>.También puede utilizar las casillas para especificar si desea realizar seguimiento de actividades, propagación de actividades o recoger información de identificación personal.  
  
 También puede especificar sesiones de registro en el cuadro de grupo **Sesión de registro**.  
  
> [!NOTE]
>  Cuando otro consumidor de seguimiento está utilizando el proveedor de seguimiento de WS\-AT, no puede crear una nueva sesión del registro para eventos de seguimiento.Cualquier intento de configurar el registro durante ese tiempo producirá el mensaje de error “No se ha podido habilitar el proveedor.Código de error: 1”.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] seguimiento y registro, vea [Administración y diagnóstico](../../../docs/framework/wcf/diagnostics/index.md).  
  
## Vea también  
 [Configuración de la compatibilidad con WS\-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)   
 [Utilidad de configuración de WS\-AtomicTransaction \(wsatConfig.exe\)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)   
 [Administración y diagnóstico](../../../docs/framework/wcf/diagnostics/index.md)