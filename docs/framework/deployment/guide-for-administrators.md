---
title: Guía de implementación de .NET Framework para administradores
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: be15ce0b0bed37da6fe400e98bfdd118c48f7ba0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716537"
---
# <a name="net-framework-deployment-guide-for-administrators"></a>Guía de implementación de .NET Framework para administradores

En este artículo paso a paso se describe cómo puede implementar un administrador del sistema .NET Framework 4.5 y sus dependencias del sistema en una red mediante Microsoft Endpoint Configuration Manager. En este artículo se supone que todos los equipos cliente de destino cumplen los requisitos mínimos para .NET Framework. Para obtener una lista de los requisitos de software y hardware para instalar .NET Framework 4.5, consulte [Requisitos de sistema](../get-started/system-requirements.md).

> [!NOTE]
> El software al que se hace referencia en este documento, a título enunciativo y en ningún caso limitativo, .NET Framework 4.5, Configuration Manager y Active Directory, está sujeto a los términos y condiciones de licencia. En estas instrucciones se asume que los usuarios con la licencia apropiada del software han leído y aceptado dichos términos y condiciones. Estas instrucciones no anulan ninguno de los términos y condiciones de dichos contratos de licencia.
>
> Para obtener información sobre el soporte técnico de .NET Framework, consulte [Directiva de ciclo soporte técnico oficial de .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) en el sitio web de soporte técnico de Microsoft.

Este tema contiene las siguientes secciones:

- [Proceso de implementación](#the_deployment_process)
- [Implementación de .NET Framework](#deploying_in_a_test_environment)
- [Crear una colección](#creating_a_collection)
- [Crear un paquete y un programa](#creating_a_package)
- [Seleccionar un punto de distribución](#select_dist_point)
- [Implementar el paquete](#deploying_package)
- [Recursos](#resources)
- [Solución de problemas](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a>Proceso de implementación

Una vez implementada la infraestructura de apoyo, se utiliza Configuration Manager para implementar el paquete redistribuible de .NET Framework en equipos de la red. La creación de la infraestructura implica crear y definir cinco áreas primarias: colecciones, un paquete y un programa para el software, puntos de distribución e implementaciones.

- Las **colecciones** son grupos de recursos de Configuration Manager, tales como usuarios, grupos de usuarios o equipos, en los que se implementa .NET Framework. Para más información, consulte [Introducción a las recopilaciones en Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) en la biblioteca de documentación de Configuration Manager.

- Los **paquetes y programas** suelen representar aplicaciones de software que se van a instalar en un equipo cliente, aunque también pueden contener archivos individuales, actualizaciones o incluso comandos individuales. Para obtener más información, consulte el tema sobre [paquetes y programas en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) en la biblioteca de documentación de Configuration Manager.

- Los **puntos de distribución** son roles del sistema de sitio de Configuration Manager que almacenan los archivos necesarios para que el software se ejecute en los equipos cliente. Cuando un cliente de Configuration Manager recibe y procesa una implementación de software, se pone en contacto con un punto de distribución para descargar el contenido asociado al software e iniciar el proceso de instalación. Para más información, vea [Aspectos básicos de la administración de contenido en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) en la biblioteca de documentación de Configuration Manager.

- Las **implementaciones** indican a los miembros correspondientes de la colección de destino especificada que instalen el paquete de software.

> [!IMPORTANT]
> Los procedimientos de este tema contienen valores típicos para crear e implementar un paquete y un programa y puede que no cubran todos los valores posibles. Para ver otras opciones de implementación de Configuration Manager, consulte la [biblioteca de documentación de Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a>Implementación de .NET Framework

Se puede usar Configuration Manager para implementar una instalación silenciosa de .NET Framework 4.5, donde los usuarios no interactúan con el proceso de instalación. Siga estos pasos:

1. [Cree una colección](#creating_a_collection).

2. [Cree un paquete y un programa para el paquete redistribuible de .NET Framework](#creating_a_package).

3. [Seleccione un punto de distribución](#select_dist_point).

4. [Implemente el paquete](#deploying_package).

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a>Crear una colección

En este paso, se seleccionan los equipos donde se implementará el paquete y el programa y se agruparán en una colección de dispositivos. Para crear una colección en Configuration Manager, puede usar reglas de pertenencia directa (donde se especifican manualmente los miembros de la colección) o reglas de consulta (donde Configuration Manager determina los miembros de la colección en función de los criterios que especifique el usuario). Para obtener más información sobre las reglas de pertenencia, incluidas las reglas de consulta y las reglas directas, consulte [Introducción a las recopilaciones en Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) en la biblioteca de documentación de Configuration Manager.

Para crear una colección:

1. En la consola de Configuration Manager, elija **Activos y compatibilidad**.

2. En el área de trabajo **Activos y compatibilidad**, elija **Recopilaciones de dispositivos**.

3. En la pestaña **Inicio** del grupo **Crear**, elija **Crear recopilación de dispositivos**.

4. En la página **General** del **Asistente para crear recopilación de dispositivos**, escriba un nombre para la colección.

5. Elija **Examinar** para especificar una recopilación de restricción.

6. En la página **Reglas de pertenencia**, elija **Agregar regla** y, a continuación, **Regla directa** para abrir el **Asistente para crear reglas de pertenencia directa**. Seleccione **Siguiente**.

7. En la página **Buscar recursos**, en la lista **Clase de recurso**, elija **Recurso del sistema**. En la lista **Nombre del atributo**, elija **Nombre**. En el campo **Valor**, escriba `%` y elija **Siguiente**.

8. En la página **Seleccionar recursos**, active la casilla de cada equipo en el que desea implementar .NET Framework. Elija **Siguiente** y finalice el asistente.

9. En la página **Reglas de pertenencia** del **Asistente para crear recopilación de dispositivos**, elija **Siguiente** y finalice el asistente.

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a>Cree un paquete y un programa para el paquete redistribuible de .NET Framework

Mediante los siguientes pasos se crea manualmente un paquete para .NET Framework redistribuible. El paquete contiene los parámetros especificados para instalar .NET Framework y la ubicación desde la que se distribuirá el paquete a los equipos de destino.

Para crear un paquete:

1. En la consola de Configuration Manager, elija **Biblioteca de software**.

2. En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.

3. En la pestaña **Inicio**, en el grupo **Crear**, elija **Crear paquete**.

4. En la página **Paquete** del **Asistente para crear paquetes y programas**, escriba la siguiente información:

    - Nombre: `.NET Framework 4.5`

    - Fabricante: `Microsoft`

    - Idioma. `English (US)`

5. Elija **Este paquete contiene archivos de origen** y, después, **Examinar** para seleccionar la carpeta local o de red que contiene los archivos de instalación de .NET Framework. Una vez seleccionada la carpeta, elija **Aceptar** y **Siguiente**.

6. En la página **Tipo de programa** del asistente, elija **Programa estándar** y, después, **Siguiente**.

7. En la página **Programa** del **Asistente para crear paquetes y programas**, escriba la siguiente información:

    1. **Nombre:** `.NET Framework 4.5`

    2. **Línea de comandos:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (las opciones de la línea de comandos se describen en la tabla que aparece después de estos pasos)

    3. **Ejecutar:** elija **Oculto**.

    4. **El programa se puede ejecutar:** elija la opción que especifica que el programa puede ejecutarse independientemente de si un usuario ha iniciado sesión.

8. En la página **Requisitos**, elija **Siguiente** para aceptar los valores predeterminados y, después, finalice el asistente.

En la tabla siguiente se describen las opciones de la línea de comandos especificadas en el paso 7.

|Opción|Description|
|------------|-----------------|
|**/q**|Establece el modo silencioso. No se requiere proporcionar ningún dato y no se muestra ningún resultado.|
|**/norestart**|Evita que el programa de instalación se reinicie automáticamente. Si usa esta opción, Configuration Manager debe controlar el reinicio del equipo.|
|**/chainingpackage** *NombreDePaquete*|Especifica el nombre del paquete que realiza el encadenamiento. Esta información se notifica con otra información de sesión de instalación para los usuarios que se hayan registrado en el Programa para la mejora de la experiencia del usuario (CEIP) de Microsoft. Si el nombre del paquete incluye espacios, use comillas dobles como delimitadores; por ejemplo: **/chainingpackage "Chaining Product"** .|

Mediante estos pasos se crea un paquete denominado .NET Framework 4.5. El programa implementa una instalación silenciosa de .NET Framework 4.5. En una instalación silenciosa, los usuarios no interactúan con el proceso de instalación y la aplicación de encadenamiento tiene que capturar el código devuelto y controlar el reinicio; vea [Getting Progress Information from an Installation Package (Obtener información de progreso de un paquete de instalación)](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a>Seleccionar un punto de distribución

Para distribuir el paquete y el programa a los equipos cliente de un servidor, deberá designar primero un sistema de sitio como punto de distribución y después distribuir el paquete al punto de distribución.

Realice los pasos siguientes para seleccionar un punto de distribución para el paquete de .NET Framework 4.5 que ha creado en la sección anterior:

1. En la consola de Configuration Manager, elija **Biblioteca de software**.

2. En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.

3. En la lista de paquetes, seleccione el paquete **.NET Framework 4.5** que creó en la sección anterior.

4. En la pestaña **Inicio**, en el grupo **Implementación**, elija **Distribuir contenido**.

5. En la pestaña **General** del **Asistente para distribuir contenido**, elija **Siguiente**.

6. En la página **Destino del contenido** del asistente, elija **Agregar** y, después, **Punto de distribución**.

7. En el cuadro de diálogo **Agregar puntos de distribución**, seleccione los puntos de distribución que hospedarán el paquete y el programa y, a continuación, elija **Aceptar**.

8. Complete el asistente.

Ahora el paquete contiene toda la información necesaria para realizar una implementación silenciosa de .NET Framework 4.5. Antes de implementar el paquete y el programa, compruebe que se haya instalado en el punto de distribución; vea la sección de supervisión de contenido de [Supervisión del contenido que se ha distribuido con Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) en la biblioteca de documentación de Configuration Manager.

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a>Implementar el paquete

Para implementar el paquete y el programa de .NET Framework 4.5:

1. En la consola de Configuration Manager, elija **Biblioteca de software**.

2. En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.

3. En la lista de paquetes, seleccione el paquete que creó denominado **.NET Framework 4.5**.

4. En la pestaña **Inicio**, en el grupo **Implementación**, elija **Implementar**.

5. En la página **General** del **Asistente para implementar software**, elija **Examinar** y, a continuación, seleccione la colección que creó anteriormente. Seleccione **Siguiente**.

6. En la página **Contenido** del asistente, compruebe que se muestra el punto desde el que desea distribuir el software y elija **Siguiente**.

7. En la página **Configuración de implementación** del asistente, confirme que la **Acción** está establecida en **Instalar** y el **Propósito** en **Requerido**. Esto garantiza que el paquete de software sea una instalación obligatoria en los equipos de destino. Seleccione **Siguiente**.

8. En la página **Programación** del asistente, especifique cuándo desea que se instale .NET Framework. Puede elegir **Nuevo** para asignar un tiempo de instalación o bien indicar al software que realice la instalación cuando el usuario inicie o cierre sesión o lo antes posible. Seleccione **Siguiente**.

9. En la página **Experiencia del usuario** del asistente, use los valores predeterminados y elija **Siguiente**.

    > [!WARNING]
    > El entorno de producción puede tener directivas que requieran selecciones distintas para la programación de distribución. Para obtener información sobre estas opciones, vea el tema sobre [la pestaña programación de las propiedades de nombre de anuncio](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).

10. En la página **Puntos de distribución** del asistente, use los valores predeterminados y elija **Siguiente**.

11. Complete el asistente. Puede supervisar el progreso de la implementación en el nodo **Implementaciones** del área de trabajo **Supervisión**.

El paquete se implementará ahora en la colección de destino y se iniciará la instalación silenciosa de .NET Framework 4.5. Para obtener información sobre los códigos de error de instalación de .NET Framework 4.5, vea la sección [Códigos devueltos](#return_codes) en este mismo tema.

<a name="resources"></a>

## <a name="resources"></a>Recursos

Para obtener más información sobre la infraestructura para probar la implementación del paquete redistribuible de .NET Framework 4.5, consulte los siguientes recursos.

**Active Directory, DNS, DHCP:**

- [Active Directory Domain Services](/windows/desktop/ad/active-directory-domain-services)

- [Sistema de nombres de dominio (DNS)](/windows-server/networking/dns/dns-top)

- [Protocolo de configuración dinámica de host (DHCP)](/windows-server/networking/technologies/dhcp/dhcp-top)

**SQL Server 2008:**

- [Instalar SQL Server 2008 (vídeo de SQL Server)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))

- [Información general sobre la seguridad de SQL Server 2008 para administradores de bases de datos](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

**System Center 2012 Configuration Manager (punto de administración, punto de distribución):**

- [Administración del sitio de System Center 2012 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [Planeación e implementación de sitio único de Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

**Cliente de System Center 2012 Configuration Manager para equipos Windows:**

- [Implementación de clientes para System Center 2012 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a>Solución de problemas

### <a name="log-file-locations"></a>Ubicaciones de archivos de registro

Los siguientes archivos de registro se generan durante la configuración de .NET Framework:

- %temp%\Microsoft .NET Framework *versión*\*.txt
- %temp%\Microsoft .NET Framework *versión*\*.html

donde *versión* es la versión de .NET Framework que va a instalar, como 4.5 o 4.7.2.

También puede especificar el directorio en el que se escriben los archivos de registro mediante la opción de la línea de comandos `/log` en el comando de instalación de .NET Framework. Para obtener más información, consulte la [Guía de implementación de .NET Framework para desarrolladores](deployment-guide-for-developers.md#command-line-options).

Puede usar la [herramienta de recopilación de registros](https://www.microsoft.com/download/details.aspx?id=12493) para recopilar los archivos de registro de .NET Framework y crear un archivo .cab comprimido que reduzca el tamaño de los archivos.

<a name="return_codes"></a>

### <a name="return-codes"></a>Códigos de retorno

En la siguiente tabla se muestra una lista de los códigos devueltos más habituales del programa de instalación redistribuible de .NET Framework 4.5. Los códigos devueltos son los mismos para todas las versiones del instalador.

Para obtener vínculos a información detallada, vea la sección siguiente, [Descargar códigos de error](#additional_error_codes).

|Código devuelto|Description|
|-----------------|-----------------|
|0|La instalación se completó correctamente.|
|1602|El usuario canceló la instalación.|
|1603|Error irrecuperable durante la instalación.|
|1641|Para completar la instalación es necesario reiniciar. Este mensaje indica que la instalación se realizó correctamente.|
|3010|Para completar la instalación es necesario reiniciar. Este mensaje indica que la instalación se realizó correctamente.|
|5100|El equipo del usuario no cumple los requisitos del sistema.|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a>Descargar códigos de error

- [Códigos de error del Servicio de transferencia inteligente en segundo plano (BITS)](/windows/desktop/Bits/bits-return-values)

- [Códigos de error del moniker de dirección URL](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- [Códigos de error de WinHttp](/windows/desktop/WinHttp/error-messages)

Otros códigos de error:

- [Códigos de error de Windows Installer](/windows/desktop/msi/error-codes)

- [Códigos de resultado del Agente de Windows Update](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))

## <a name="see-also"></a>Vea también

- [Guía de implementación para desarrolladores](deployment-guide-for-developers.md)
- [Requisitos del sistema](../get-started/system-requirements.md)
