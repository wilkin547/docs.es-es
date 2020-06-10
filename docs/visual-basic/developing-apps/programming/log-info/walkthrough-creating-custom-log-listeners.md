---
title: Crear agentes de escucha de registro personalizados
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 5a140607a4fe7e1e13de54e8d56cab53e52aaa2a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398271"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic)

En este tutorial se muestra cómo crear un agente de escucha de registro personalizado y configurarlo para escuchar la salida del objeto `My.Application.Log`.

## <a name="getting-started"></a>Introducción

Los agentes de escucha de registro deben heredar de la clase <xref:System.Diagnostics.TraceListener>.

#### <a name="to-create-the-listener"></a>Para crear el agente de escucha

- En la aplicación, cree una clase denominada `SimpleListener` que herede de <xref:System.Diagnostics.TraceListener>.

     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]

     Los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, requeridos por la clase base, llame a `MsgBox` para mostrar su entrada.

     El atributo <xref:System.Security.Permissions.HostProtectionAttribute> se aplica a los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, para que sus atributos coincidan con los métodos de clase base. El atributo <xref:System.Security.Permissions.HostProtectionAttribute> permite al host que ejecuta el código determinar que el código expone sincronización de protección de host.

    > [!NOTE]
    > El atributo <xref:System.Security.Permissions.HostProtectionAttribute> solo es eficaz en aplicaciones no administradas que hospedan Common Language Runtime e implementan protección de host, como SQL Server.

Para asegurarse de que `My.Application.Log` usa su agente de escucha de registro, debe asignar un nombre seguro al ensamblado que contiene el agente de escucha de registro.

En el procedimiento siguiente se proporcionan algunos pasos sencillos para crear un ensamblado de agente de escucha de registro con nombre seguro. Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../../../../standard/assembly/create-use-strong-named.md).

#### <a name="to-strongly-name-the-log-listener-assembly"></a>Para asignar un nombre seguro al ensamblado de agente de escucha de registro

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto** , elija **Propiedades**.

2. Haga clic en la pestaña **Firma**.

3. Active la casilla **Firmar el ensamblado** .

4. Seleccione **\<New>** en la lista desplegable **Elija un archivo de clave de nombre seguro**.

     Se abre el cuadro de diálogo **Crear clave de nombre seguro**.

5. Especifique un nombre para el archivo de clave en el cuadro **Nombre del archivo de clave**.

6. Escriba una contraseña en los cuadros **Escribir contraseña** y **Confirmar contraseña**.

7. Haga clic en **Aceptar**.

8. Vuelva a compilar la aplicación.

## <a name="adding-the-listener"></a>Agregar el agente de escucha

Ahora que el ensamblado tiene un nombre seguro, debe determinar el nombre seguro del agente de escucha para que `My.Application.Log` use el agente de escucha de registro.

El formato de un tipo con nombre seguro es el siguiente.

\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name>

#### <a name="to-determine-the-strong-name-of-the-listener"></a>Para determinar el nombre seguro del agente de escucha

- En el código siguiente se muestra cómo determinar el nombre de tipo seguro para `SimpleListener`.

     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]

     El nombre seguro del tipo depende de su proyecto.

Con el nombre seguro, puede agregar el agente de escucha a la colección de agente de escucha de registro de `My.Application.Log`.

#### <a name="to-add-the-listener-to-myapplicationlog"></a>Para agregar el agente de escucha a My.Application.Log

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

     o bien

     Si hay un archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>` . La sección `<sources>` se encuentra en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

3. Agregue este elemento a la sección `<listeners>`:

    ```xml
    <add name="SimpleLog" />
    ```

4. Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

5. Agregue este elemento a dicha sección `<sharedListeners>` :

    ```xml
    <add name="SimpleLog" type="SimpleLogStrongName" />
    ```

     Cambie el valor de `SimpleLogStrongName` para que sea el nombre seguro del agente de escucha.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Trabajar con registros de aplicaciones](working-with-application-logs.md)
- [Cómo: Registrar excepciones](how-to-log-exceptions.md)
- [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md)
- [Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información](walkthrough-changing-where-my-application-log-writes-information.md)
