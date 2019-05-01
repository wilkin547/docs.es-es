---
title: Complemento MMC de configuración de WS-AtomicTransaction
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: b1d86fa57b31d1f9be12f76c28f9d042e7e28e24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052565"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>Complemento MMC de configuración de WS-AtomicTransaction
El complemento MMC de configuración de WS-AtomicTransaction se utiliza para configurar una parte de los valores WS-AtomicTransaction en los equipos local remoto.  
  
## <a name="remarks"></a>Comentarios  
 Si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], se encuentra el complemento MMC navegando a **Control Panel/Administrative Tools/servicios de componentes /**, hacer clic **Mi PC**, y seleccionar **propiedades**. Ésta es la misma ubicación donde puede configurar MSDTC. Las opciones disponibles para la configuración se agrupan bajo el **WS-AT** ficha.  
  
 Si está ejecutando Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], puede encontrarse en el complemento MMC haciendo clic en el **iniciar** botón y escriba `dcomcnfg.exe` en el **búsqueda** cuadro. Cuando se abre la consola MMC, vaya a la **mi pc\coordinador de transacciones local DTC** nodo, haga clic y seleccione **propiedades**. Las opciones disponibles para la configuración se agrupan bajo el **WS-AT** ficha.  
  
 Los pasos anteriores se utilizan para iniciar el complemento para configurar un equipo local. Si desea configurar un equipo remoto, debe buscar el nombre del equipo remoto en **Control Panel/Administrative Tools/servicios de componentes /** y llevar a cabo pasos similares si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Si está ejecutando Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], siga los pasos anteriores para Vista y [!INCLUDE[lserver](../../../includes/lserver-md.md)], pero usar el **transacciones DISTRIBUIDAS\DTC** nodo bajo el nodo del equipo remoto.  
  
 Para utilizar la interfaz de usuario proporcionada por la herramienta, tiene que registrar el archivo WsatUI.dll, que se encuentra en la ruta de acceso siguiente  
  
 **%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**  
  
 El comando siguiente puede hacer el registro.  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 Puede utilizar esta herramienta para modificar los valores básicos de WS-AtomicTransaction. Por ejemplo, puede habilitar y deshabilitar la compatibilidad de protocolo de WS-AtomicTransaction, configurar los puertos del HTTP para WS-AT, enlazar un Certificado SSL al puerto HTTP, configurar los certificados especificando los nombres de sujeto de certificado, seleccionar el modo de seguimiento y establecer los tiempos de espera predeterminado y máximo.  
  
 Si tiene que configurar la compatibilidad de WS-AtomicTransaction solo en el equipo local, puede usar la versión de línea de comandos de esta herramienta. Para obtener más información acerca de la herramienta de línea de comandos, consulte el [WS-AtomicTransaction Configuration Utility (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md) tema.  
  
 Debe tener en cuenta que tanto el complemento MMC como la herramienta de la línea de comandos no permiten configurar todos los valores WS-AT. Esta configuración sólo se puede editar modificando directamente el registro. Para obtener más información acerca de estos valores del registro, consulte [configurar WS-Atomic Transaction Support](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### <a name="user-interface-description"></a>Descripción de la interfaz de usuario  
 **Habilitar la compatibilidad de red de WS-AtomicTransaction**:  
  
 Esta casilla habilita o deshabilita todos los componentes GUI de este complemento.  
  
 Antes de marcar la casilla, debería asegurarse de que el acceso DTC a red está habilitado con comunicación entrante o saliente, o ambas. Este valor se puede comprobar en el **seguridad** ficha del complemento MSDTC.  
  
#### <a name="network-group-box"></a>Cuadro Grupo de red  
 Puede especificar el puerto HTTPS y configuración de seguridad adicional como cifrado SSL en el grupo de red. Este grupo está deshabilitado (atenuado) si no están habilitadas las transacciones de red DTC.  
  
 **Puerto HTTPS**  
  
 Éste es el valor del puerto HTTPS utilizado para WS-AT. El valor debe ser un número en el intervalo 1-65535 (para representar un puerto válido). Al cambiar el puerto HTTP se modifica la configuración de servicio HTTP, lo que significa que se libera la dirección de servicio WS-AT previamente utilizada y se registra una dirección de servicio WS-AT nueva basado del nuevo puerto. Además, el puerto recientemente seleccionado se cifra con el certificado seleccionado actualmente para cifrado SSL.  
  
> [!NOTE]
>  Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones. Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.  
  
 Si habilita el firewall después de configurar WS-AT, debe ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro. Si deshabilita el firewall después de configurar, WS-AT continúa funcionando sin entrada adicional.  
  
 **Certificado de punto de conexión**  
  
 Al hacer clic en el **seleccione** botón muestra una lista con los certificados actualmente disponibles en el equipo Local, lo que permite al usuario seleccionar el certificado que se puede usar para el cifrado SSL. Los certificados tienen que tener una clave privada. De lo contrario, recibirá un mensaje de error.  
  
> [!NOTE]
>  Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
 **Cuentas autorizadas**  
  
 Al hacer clic en el **seleccione** botón invoca el editor de lista de Control de acceso de Windows, donde puede especificar el usuario o grupo que puede participar en WS-Atomic transactions marcando la **permitir** o **Deny** cuadro el **participar** grupo de permisos.  
  
 **Certificados autorizados**  
  
 Al hacer clic en el **seleccione** botón muestra una lista de certificados actualmente disponibles en el equipo local. Puede seleccionar a continuación qué identidades del certificado pueden participar en WS-Atomic Transactions.  
  
#### <a name="timeout-group-box"></a>Cuadro de grupo Tiempo de espera  
 El **tiempo de espera** cuadro de grupo le permite especificar el tiempo de espera predeterminado y máximo para una transacción WS-Atomic. Un valor válido para el tiempo de espera de salida está entre 1 y 3600. Un valor válido para el tiempo de espera de entrada está entre 0 y 3600.  
  
#### <a name="tracing-and-logging-group-box"></a>Cuadro de grupo Seguimiento y registro  
 El **seguimiento y registro** cuadro de grupo le permite configurar el nivel de registro y seguimiento deseado.  
  
 Al hacer clic en el **opciones** botón invoca una página donde puede especificar una configuración adicional.  
  
 El **nivel de seguimiento** cuadro de combinación permite elegir cualquier valor válido de la <xref:System.Diagnostics.TraceLevel> enumeración. También puede utilizar las casillas para especificar si desea realizar seguimiento de actividades, propagación de actividades o recoger información de identificación personal.  
  
 También puede especificar sesiones de registro en el **sesión registro** cuadro de grupo.  
  
> [!NOTE]
>  Cuando otro consumidor de seguimiento está utilizando el proveedor de seguimiento de WS-AT, no puede crear una nueva sesión del registro para eventos de seguimiento. Cualquier intento de configurar el registro durante ese tiempo producirá el mensaje de error “No se ha podido habilitar el proveedor. Código de error: 1".  
  
 Para obtener más información acerca del seguimiento y registro, consulte [administración y diagnóstico](../../../docs/framework/wcf/diagnostics/index.md).  
  
## <a name="see-also"></a>Vea también

- [Configuración de la compatibilidad con WS-Atomic Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
- [Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Administración y diagnóstico](../../../docs/framework/wcf/diagnostics/index.md)
