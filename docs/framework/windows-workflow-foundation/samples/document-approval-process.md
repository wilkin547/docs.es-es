---
title: Proceso de aprobación de un documento
description: En este ejemplo se muestran muchas características de Windows Workflow Foundation y Windows Communication Foundation en un escenario de proceso de aprobación de documentos.
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: 18b4f978e9234daf22395f0d2f6f0889d0edf966
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421415"
---
# <a name="document-approval-process"></a>Proceso de aprobación de un documento

Este ejemplo muestra el uso conjunto de muchas características de Windows Workflow Foundation (WF) y Windows Communication Foundation (WCF). Juntas implementan un escenario de proceso de aprobación de un documento. Una aplicación cliente puede enviar documentos para su aprobación y aprobar documentos. Existe una aplicación de administrador de aprobaciones para facilitar las comunicaciones entre los clientes y aplicar las reglas del proceso de aprobación. El proceso de aprobación es un flujo de trabajo que puede ejecutar varios tipos de aprobación. Existen actividades para obtener una aprobación única, una aprobación de quórum (un porcentaje de un conjunto de aprobadores) y un proceso de aprobación compleja que consta de una aprobación de quórum y una aprobación única en una secuencia.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a>Detalles del ejemplo

En el gráfico siguiente se muestra el flujo de trabajo del proceso de aprobación de documentos:

![Flujo de trabajo del proceso de aprobación de un documento](./media/document-approval-process/document-approval-process.jpg)

Desde la perspectiva del cliente, el proceso de aprobación funciona del siguiente modo:

1. Un cliente realiza una suscripción para convertirse en usuario en el sistema del proceso de aprobación.

2. Un cliente WCF envía a un servicio WCF hospedado por la aplicación de administrador de aprobaciones.

3. Se devuelve un Id. de usuario único al cliente. El cliente puede participar ahora en los procesos de aprobación.

4. Una vez admitido, un cliente puede enviar un documento para su aprobación mediante un proceso de aprobación única, de quórum o compleja.

5. Al hacer clic en un botón de la interfaz del cliente, se inicia una instancia de flujo de trabajo en un host de servicio de flujo de trabajo del cliente.

6. El flujo de trabajo envía una solicitud de aprobación a la aplicación de administrador de aprobaciones.

7. El administrador del flujo de trabajo inicia un flujo de trabajo por su parte para representar un proceso de aprobación.

8. Una vez ejecutado el flujo de trabajo de aprobación del administrador, los resultados se devuelven al cliente.

9. El cliente muestra los resultados.

10. Un cliente puede recibir una solicitud de aprobación y responder a la solicitud en cualquier momento.

11. Un servicio WCF hospedado en el cliente puede recibir una solicitud de aprobación de la aplicación del administrador de aprobaciones.

12. La información del documento se presenta en el cliente para revisión.

13. El usuario puede aprobar o rechazar el documento.

14. Un cliente de WCF se usa para devolver una respuesta de aprobación a la aplicación de administrador de aprobaciones.

Desde el punto de vista de la aplicación de administrador de aprobaciones, el proceso de aprobación funciona del siguiente modo:

1. Un cliente solicita al sistema del proceso de aprobación participar.

2. Un servicio WCF en el administrador de aprobaciones recibe una solicitud para formar parte del sistema del proceso de aprobación.

3. Se genera un identificador único para el cliente. La información sobre el usuario se almacena en una base de datos.

4. El identificador único se envía al usuario.

5. Se recibe una solicitud de aprobación. El administrador de aprobaciones ejecuta un proceso de aprobación.

6. El administrador de aprobaciones recibe una solicitud de aprobación, lo que inicia un nuevo flujo de trabajo.

7. Según el tipo de solicitud (simple, quórum o compleja), se ejecuta una actividad diferente.

8. Las actividades Send y Receive con correlación se utilizan para enviar la solicitud de aprobación al cliente para su revisión y recibir la respuesta.

9. El resultado del flujo de trabajo del proceso de aprobación se envía al cliente.

## <a name="using-the-sample"></a>Utilizar el ejemplo

##### <a name="to-set-up-the-database"></a>Para configurar la base de datos

1. Desde un símbolo del sistema de Visual Studio 2010 abierto con privilegios de administrador, vaya a esta carpeta DocumentApprovalProcess y ejecute setup. cmd.

##### <a name="to-set-up-the-application"></a>Para configurar la aplicación

1. Con Visual Studio 2010, abra el archivo de solución DocumentApprovalProcess. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar la solución, inicie la aplicación del administrador de aprobaciones; para ello, haga clic con el botón secundario en el proyecto ApprovalManager en el **Explorador de soluciones** y haga clic en **depurar** -> **iniciar** nueva instancia en el menú contextual.

    Espere a que el resultado del administrador le indique que está listo.

##### <a name="to-run-the-single-approval-scenario"></a>Para ejecutar el escenario de aprobación única

1. Abra un símbolo del sistema con permisos de administrador.

2. Navegue al directorio que contiene la solución.

3. Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute dos instancias de ApprovalClient.exe.

4. Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .

5. Escriba cualquier nombre de usuario y haga clic en **suscribirse**. Para un cliente, use `UserType1` y para el otro, escriba `UserType2`.

6. En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido. Haga clic en **solicitar aprobación**.

7. En el cliente `UserType2`, aparecerá un documento a la espera de aprobación. Selecciónelo y presione **aprobar** o **rechazar**. Los resultados deberían mostrarse en el cliente `UserType1`.

##### <a name="to-run-the-quorum-approval-scenario"></a>Para ejecutar el escenario de aprobación de quórum

1. Abra un símbolo del sistema con permisos de administrador.

2. Navegue al directorio que contiene la solución.

3. Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute tres instancias de ApprovalClient.exe.

4. Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .

5. Escriba cualquier nombre de usuario y haga clic en **suscribirse**. Para un cliente, use `UserType1` y para los otros dos, escriba `UserType2`.

6. En el cliente `UserType1`, seleccione el tipo de aprobación de quórum en el menú desplegable y escriba un nombre de documento y su contenido. Haga clic en **solicitar aprobación**. Este tipo de aprobación requieres que los dos clientes `UserType2` aprueben o rechacen el documento. Aunque los dos clientes `UserType2` deben responder, solo uno de ellos necesita aprobar el documento para que se considere aprobado.

7. En los clientes `UserType2`, aparecerá un documento a la espera de aprobación. Selecciónelo y presione **aprobar** o **rechazar**. Los resultados deberían mostrarse en el cliente `UserType1`.

##### <a name="to-run-the-complex-approval-scenario"></a>Para ejecutar el escenario de aprobación compleja

1. Abra un símbolo del sistema con permisos de administrador.

2. Navegue al directorio que contiene la solución.

3. Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute cuatro instancias de ApprovalClient.exe.

4. Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .

5. Escriba cualquier nombre de usuario y haga clic en **suscribirse**. Para un cliente, use `UserType1`, para los otros dos, escriba `UserType2` y en el último, use `UserType3`.

6. En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido. Haga clic en **solicitar aprobación**.

7. En los clientes `UserType2`, aparecerá un documento a la espera de aprobación. Selecciónelo y presione **aprobar**; el documento se pasa al `UserType3` cliente.

    Si el primer quórum `UserType2` aprueba el documento, el documento se pasa al cliente `UserType3`.

8. Apruebe o rechace el documento en el cliente `UserType3`. Los resultados deberían mostrarse en el cliente `UserType1`.

##### <a name="to-clean-up"></a>Para realizar una limpieza

1. Desde un símbolo del sistema de Visual Studio 2010, vaya a la carpeta DocumentApprovalProcess y ejecute Cleanup. cmd.
