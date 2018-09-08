---
title: Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: 1b30da34f7c85cccd98b18cd32b81c83630989b2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216137"
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a>Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo

A veces es necesario que un servicio de flujo de trabajo obtenga información de otro servicio de flujo de trabajo. En este tema se muestra cómo llamar a un servicio de flujo de trabajo desde otro. En este tema, crearemos dos servicios de flujo de trabajo; uno que tiene un método que invierte la cadena de entrada y otro que convierte la cadena de entrada en letras mayúsculas después de invertir la cadena que utiliza el primer servicio.

### <a name="to-create-the-reverser-workflow-service"></a>Crear el servicio de flujo de trabajo Reverser

1.  Abra Visual Studio.

2.  Seleccione **archivo** > **nuevo proyecto**. En el **flujo de trabajo** nodo en el **plantillas instaladas** panel, seleccione **aplicación de servicio de flujo de trabajo de WCF**. Nombre de la solución `NestedServices` y, a continuación, haga clic en **Aceptar**.

3.  En **servidores**, asegúrese de que **usar servidor Web de IIS Local** está seleccionada. Haga clic en **crear directorio Virtual**. Haga clic en **Aceptar** en el cuadro de diálogo que indica que el directorio virtual se creó correctamente.

4.  En el Explorador de soluciones, cambie el nombre de Service1.xamlx a `StringReverserService.xamlx`.

5.  En el **las propiedades del proyecto** página para el nuevo proyecto, haga clic en el **Web** ficha. Establecer el **acción de inicio** a **página específica**y seleccione StringReverserService.xamlx como la página de inicio.

6.  Abra StringReverserService.xamlx en el diseñador y elimine las actividades `ReceiveRequest` y `SendReply` existentes, y a continuación arrastre una actividad `ReceiveAndSendReply` a la actividad de secuencia existente.

    1.  Establecer el **OperationName** en ReverseString.

    2.  Establecer el **ServiceContractName** en IReverseString.

    3.  Seleccione el **CanCreateInstance** casilla de verificación.

7.  Seleccione el **SequentialService** actividad y, a continuación, haga clic en el **Variables** ficha en la parte inferior del diseñador. Cree dos nuevas variables denominadas que StringToReverse y ReversedStringToReturn de tipo String.

8.  Haga clic en el **definir** vincular en el **recepción** actividad. Haga clic en el **parámetros**y cree un parámetro denominado InputString de tipo String que se asigne a StringToReverse.

9. Haga clic en el **definir** vincular en el **SendReplyToReceive** actividad. Haga clic en el **parámetros**y cree un parámetro denominado ReversedString del tipo String, asignado a ReversedStringToReturn.

10. Para implementar la lógica para el servicio, cree en el proyecto una nueva clase llamada StringLibrary.  Reemplace la definición de clase por el código siguiente.

    ```
    public class StringLibrary
        {
            public static String ReverseString(string StringToReverse)
            {
                char[] charArray = StringToReverse.ToCharArray();
                Array.Reverse(charArray);
                return new String(charArray);
            }
        }
    ```

11. Para llamar al método ReverseString en la entrada, arrastre un **InvokeMethod** actividad desde el cuadro de herramientas hasta el espacio entre el **recepción** y **SendReply** actividades. Establezca las propiedades de la actividad de la manera siguiente:

    1.  **MethodName**: ReverseString

    2.  **Resultado**: ReversedStringToReturn

    3.  **Parámetros**: crear un nuevo parámetro con un **dirección** de In, un **tipo** de cadena y un **valor** de StringToReverse.

    4.  **TargetType**: NestedServices.StringLibrary

12. Compruebe el servicio presionando F5. En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString(). En el panel de la solicitud, escriba `Sample` para el valor del parámetro InputString. Haga clic en **invocar**. El servicio debería devolver "elpmaS".

### <a name="to-create-the-uppercaser-workflow-service"></a>Crear el servicio de flujo de trabajo UpperCaser

1.  Haga clic en el proyecto NestedServices y seleccione **agregar** > **nuevo elemento**. En el **flujo de trabajo** nodo, seleccione **servicio de flujo de trabajo de WCF**y el nombre del nuevo servicio `UpperCaserService`. Haga clic en **Agregar**. Esto debería agregar al proyecto un nuevo servicio de flujo de trabajo llamado UpperCaserService.xamlx.

2.  Abra UpperCaserService.xamlx en el diseñador y elimine existente **ReceiveRequest** y `SendReply` actividades y arrastre un `ReceiveAndSendReply` actividad a la actividad de secuencia existente.

    1.  Establecer el **OperationName** en UpperCaseString.

    2.  Establecer el **ServiceContractName** en IUpperCaseString.

    3.  Seleccione el **CanCreateInstance** casilla de verificación.

3.  Seleccione la actividad SequentialService y, a continuación, haga clic en el **Variables** ficha en la parte inferior del diseñador. Cree tres nuevas variables denominadas que StringToUpper, StringToReverse y StringToReturn de tipo String.

4.  Haga clic en el **definir** vincular en el **recepción** actividad. Haga clic en el **parámetros**y cree un parámetro denominado InputString de tipo String que se asigne a StringToUpper.

5.  Haga clic en el **definir** vincular en el **SendReplyToReceive** actividad. Haga clic en el **parámetros**y cree un parámetro denominado ModifiedString del tipo String, asignado a StringToReturn.

6.  Para implementar la lógica para el servicio, cree un nuevo método en la clase StringLibrary utilizando el siguiente código.

    ```
    public static String UpperCaseString(string StringToUpperCase)
    {
         return StringToUpperCase.ToUpper();

    }
    ```

7.  Para llamar al método UpperCaseString en la entrada, arrastre un **InvokeMethod** actividad desde el cuadro de herramientas hasta el espacio entre el **recepción** y **SendReply** actividades. Establezca las propiedades de la actividad de la manera siguiente:

    1.  **MethodName**: UpperCaseString

    2.  **Resultado**: StringToReverse

    3.  **Parámetros**: crear un nuevo parámetro con un **dirección** de In, un **tipo** de cadena y un **valor** de StringToUpper.

    4.  **TargetType**: NestedServices.StringLibrary

8.  Llamaremos ahora al primer servicio en la cadena modificada. Haga clic en el proyecto y seleccione **agregar** > **referencia de servicio**. Agregar una referencia de servicio al servicio en http://localhost/NestedServices/StringReverserService.xamlx y compile el proyecto para crear una actividad personalizada para tener acceso al primer servicio Web.

9. Arrastre una instancia de la nueva actividad al flujo de trabajo entre el **InvokeMethod** actividad y el **SendReplyToReceive** actividades. Asigne la variable StringToReverse a la propiedad InputString de la nueva actividad y la variable StringToReturn a la propiedad StringToReturn.

10. Abra la página de propiedades para el proyecto NestedServices y cambie el **página específica** en el **Web** ficha a UpperCaserService.xamlx.

11. Compruebe el servicio presionando F5. En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString(). En el panel de la solicitud, escriba `Sample` para el valor del parámetro InputString. Haga clic en **invocar**. El servicio debería devolver "ELPMAS".

### <a name="to-create-a-client-to-call-the-services"></a>Crear un cliente para que llame al servicio

1.  Agregue un nuevo proyecto de aplicación de consola llamado Cliente a la solución.

2.  Haga clic en el proyecto de cliente y seleccione **agregar** > **referencia de servicio**. En la ventana que aparece, haga clic en **Discover**. Seleccione StringReverserService.xamlx y escriba ReverseService como el espacio de nombres.  Haga clic en **Aceptar**.

3.  Reemplace el método Main en Program.cs con el siguiente código.

    ```
    static void Main(string[] args)
    {
        Console.Write("Input string to process:");
        String input = Console.ReadLine();
        var service = new ReverseService.ReverseStringClient();
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));
        Console.ReadKey();
    }
    ```