---
description: 'Más información acerca de: WS-AtomicTransaction complemento MMC de configuración'
title: Complemento MMC de configuración de WS-AtomicTransaction
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: 5f1ac32a98b93a3ec3edb9cfa31ae0ebf424aba8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676305"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>Complemento MMC de configuración de WS-AtomicTransaction

El complemento MMC de configuración de WS-AtomicTransaction se usa para configurar una parte de la configuración de WS-AtomicTransaction en equipos locales y remotos.

## <a name="remarks"></a>Observaciones

Si está ejecutando Windows XP o Windows Server 2003, el complemento MMC se puede encontrar en **Panel de control/herramientas administrativas/servicios de componentes/**, haciendo clic con el botón derecho en **mi PC** y seleccionando **propiedades**. Ésta es la misma ubicación donde puede configurar MSDTC. Las opciones disponibles para la configuración se agrupan en la pestaña **WS-at** .

 Si está ejecutando Windows Vista o Windows Server 2008, puede encontrar el complemento MMC haciendo clic en el botón **Inicio** y escribiendo en `dcomcnfg.exe` el cuadro de **búsqueda** . Cuando se abra MMC, desplácese hasta el nodo **My Computer\Distributed Transaction COORDINATOR\LOCAL DTC** , haga clic con el botón derecho y seleccione **propiedades**. Las opciones disponibles para la configuración se agrupan en la pestaña **WS-at** .

 Los pasos anteriores se utilizan para iniciar el complemento para configurar un equipo local. Si desea configurar un equipo remoto, debe buscar el nombre del equipo remoto en **Panel de control/herramientas administrativas/servicios de componentes/** y realizar pasos similares si está ejecutando Windows XP o windows Server 2003. Si está ejecutando Windows Vista o Windows Server 2008, siga los pasos anteriores para vista y Windows Server 2008, pero use el nodo **DTC (Coordinator\Local de transacciones distribuidas** ) en el nodo del equipo remoto.

 Para utilizar la interfaz de usuario proporcionada por la herramienta, tiene que registrar el archivo WsatUI.dll, que se encuentra en la ruta de acceso siguiente

 **%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**

 El comando siguiente puede hacer el registro.

```console
regasm.exe /codebase WsatUI.dll
```

 Puede utilizar esta herramienta para modificar los valores básicos de WS-AtomicTransaction. Por ejemplo, puede habilitar y deshabilitar la compatibilidad de protocolo de WS-AtomicTransaction, configurar los puertos del HTTP para WS-AT, enlazar un Certificado SSL al puerto HTTP, configurar los certificados especificando los nombres de sujeto de certificado, seleccionar el modo de seguimiento y establecer los tiempos de espera predeterminado y máximo.

 Si solo debe configurar la compatibilidad con WS-AtomicTransaction en el equipo local, puede usar la versión de línea de comandos de esta herramienta. Para obtener más información sobre la herramienta de línea de comandos, vea el tema [utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md) .

 Debe tener en cuenta que tanto el complemento MMC como la herramienta de la línea de comandos no permiten configurar todos los valores WS-AT. Esta configuración sólo se puede editar modificando directamente el registro. Para obtener más información acerca de esta configuración del registro, consulte Configuración de la [compatibilidad con transacciones de WS-Atomic](./feature-details/configuring-ws-atomic-transaction-support.md).

### <a name="user-interface-description"></a>Descripción de la interfaz de usuario

**Habilitar la compatibilidad con redes de WS-Atomic de transacciones**:

 Esta casilla habilita o deshabilita todos los componentes GUI de este complemento.

 Antes de marcar la casilla, debería asegurarse de que el acceso DTC a red está habilitado con comunicación entrante o saliente, o ambas. Este valor se puede comprobar en la pestaña **seguridad** del complemento MSDTC.

#### <a name="network-group-box"></a>Cuadro Grupo de red

Puede especificar el puerto HTTPS y configuración de seguridad adicional como cifrado SSL en el grupo de red. Este grupo está deshabilitado (atenuado) si no están habilitadas las transacciones de red DTC.

 **Puerto HTTPS**

 Éste es el valor del puerto HTTPS utilizado para WS-AT. El valor debe ser un número en el intervalo 1-65535 (para representar un puerto válido). Al cambiar el puerto HTTP se modifica la configuración de servicio HTTP, lo que significa que se libera la dirección de servicio WS-AT previamente utilizada y se registra una dirección de servicio WS-AT nueva basado del nuevo puerto. Además, el puerto recientemente seleccionado se cifra con el certificado seleccionado actualmente para cifrado SSL.

> [!NOTE]
> Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones. Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.

 Si habilita el firewall después de configurar WS-AT, debe ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro. Si deshabilita el firewall después de configurar, WS-AT continúa funcionando sin entrada adicional.

 **Certificado de extremo**

 Al hacer clic en el botón **seleccionar** , se muestra una lista con los certificados disponibles actualmente en el equipo local, lo que permite al usuario seleccionar el certificado que se puede usar para el cifrado SSL. Los certificados tienen que tener una clave privada. De lo contrario, recibirá un mensaje de error.

> [!NOTE]
> Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.

 **Cuentas autorizadas**

 Al hacer clic en el botón **seleccionar** se invoca el editor de lista de Access Control de Windows, donde puede especificar el usuario o grupo que puede participar en WS-Atomic transacciones activando el cuadro **permitir** o **denegar** en el grupo de permisos **participar** .

 **Certificados autorizados**

 Al hacer clic en el botón **seleccionar** , se muestra una lista de los certificados disponibles actualmente en LocalMachine. Puede seleccionar a continuación qué identidades del certificado pueden participar en WS-Atomic Transactions.

#### <a name="timeout-group-box"></a>Cuadro de grupo Tiempo de espera

El cuadro grupo de **tiempo de espera** permite especificar el tiempo de espera predeterminado y máximo para una transacción WS-Atomic. Un valor válido para el tiempo de espera de salida está entre 1 y 3600. Un valor válido para el tiempo de espera de entrada está entre 0 y 3600.

#### <a name="tracing-and-logging-group-box"></a>Cuadro de grupo Seguimiento y registro

El cuadro de grupo **seguimiento y registro** permite configurar el nivel de seguimiento y de registro deseado.

 Al hacer clic en el botón **Opciones** , se invoca una página en la que puede especificar valores de configuración adicionales.

 El cuadro combinado de **nivel de seguimiento** permite elegir entre cualquier valor válido de la <xref:System.Diagnostics.TraceLevel> enumeración. También puede utilizar las casillas para especificar si desea realizar seguimiento de actividades, propagación de actividades o recoger información de identificación personal.

 También puede especificar sesiones de registro en el cuadro grupo de **sesiones de registro** .

> [!NOTE]
> Cuando otro consumidor de seguimiento está utilizando el proveedor de seguimiento de WS-AT, no puede crear una nueva sesión del registro para eventos de seguimiento. Cualquier intento de configurar el registro durante ese tiempo producirá el mensaje de error “No se ha podido habilitar el proveedor. Código de error: 1”.

 Para obtener más información sobre el seguimiento y el registro, vea [Administración y diagnósticos](./diagnostics/index.md).

## <a name="see-also"></a>Vea también

- [Configuración de la compatibilidad con WS-Atomic Transaction](./feature-details/configuring-ws-atomic-transaction-support.md)
- [Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Administración y diagnóstico](./diagnostics/index.md)
