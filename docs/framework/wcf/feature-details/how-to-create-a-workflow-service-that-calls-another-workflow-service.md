---
title: "Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo
A veces es necesario que un servicio de flujo de trabajo obtenga información de otro servicio de flujo de trabajo.En este tema se muestra cómo llamar a un servicio de flujo de trabajo desde otro.En este tema, crearemos dos servicios de flujo de trabajo; uno que tiene un método que invierte la cadena de entrada y otro que convierte la cadena de entrada en letras mayúsculas después de invertir la cadena que utiliza el primer servicio.  
  
### Crear el servicio de flujo de trabajo Reverser  
  
1.  Ejecute [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] como administrador.  
  
2.  Seleccione **Archivo**, **Nuevo proyecto**.Bajo el nodo **Flujo de trabajo** en el panel **Plantillas instaladas**, seleccione **Aplicación de servicio de flujo de trabajo WCF**.Asigne el nombre `NestedServices` a la solución y, a continuación, haga clic en **Aceptar**.  
  
3.  En **Servidores**, asegúrese de que está seleccionado **Usar servidor web de IIS local**.Haga clic en **Crear directorio virtual**.Haga clic en **Aceptar** en el cuadro de diálogo que dice que se creó el directorio virtual se creó correctamente.  
  
4.  En el Explorador de soluciones, cambie el nombre de Service1.xamlx a `StringReverserService.xamlx`.  
  
5.  En la página **Propiedades del proyecto** correspondiente al nuevo proyecto, haga clic en la pestaña **Web**.Configure **Acción de inicio** en **Página específica** y seleccione StringReverserService.xamlx como la página para iniciar.  
  
6.  Abra StringReverserService.xamlx en el diseñador y elimine las actividades `SendReply` y `ReceiveRequest` existentes, y a continuación arrastre una actividad `ReceiveAndSendReply` a la actividad de secuencia existente.  
  
    1.  Configure **OperationName** en ReverseString.  
  
    2.  Configure **ServiceContractName** en IReverseString.  
  
    3.  Seleccione el cuadro de diálogo **CanCreateInstance**.  
  
7.  Seleccione la actividad **SequentialService** y, a continuación, haga clic en la pestaña **Variables** en la parte inferior del diseñador.Cree dos nuevas variables denominadas que StringToReverse y ReversedStringToReturn de tipo String.  
  
8.  Haga clic en el vínculo **Definir** en la actividad **Receive**.Haga clic en **Parámetros** y cree un parámetro denominado InputString de tipo String que se asigne a StringToReverse.  
  
9. Haga clic en el vínculo **Definir** en la actividad **SendReplyToReceive**.Haga clic en **Parámetros** y cree un parámetro denominado ReversedString del tipo String, asignado a ReversedStringToReturn.  
  
10. Para implementar la lógica para el servicio, cree en el proyecto una nueva clase llamada StringLibrary.Reemplace la definición de clase  por el código siguiente.  
  
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
  
11. Para llamar al método ReverseString en la entrada, arrastre una actividad **InvokeMethod** desde el cuadro de herramientas hasta el espacio entre las actividades **Receive** y **SendReply**.Establezca las propiedades de la actividad de la manera siguiente:  
  
    1.  **MethodName**: ReverseString  
  
    2.  **Resultado**: ReversedStringToReturn  
  
    3.  **Parámetros**: Cree un nuevo parámetro con una **Dirección** de In, un **Tipo** de String y un **Valor** de StringToReverse.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. Compruebe el servicio presionando F5.En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString\(\).En el panel Solicitud, escriba `Ejemplo` para el valor del parámetro InputString.Haga clic en **Invocar**.El servicio debería devolver "elpmaS".  
  
### Crear el servicio de flujo de trabajo UpperCaser  
  
1.  Haga clic en el proyecto NestedServices con el botón secundario, seleccione **Agregar** y, a continuación, **Nuevo elemento**.En el nodo **Flujo de trabajo**, seleccione **Servicio de flujo de trabajo de WCF** y dé al nuevo servicio el nombre `UpperCaserService`.Haga clic en **Agregar**.Esto debería agregar al proyecto un nuevo servicio de flujo de trabajo llamado UpperCaserService.xamlx.  
  
2.  Abra UpperCaserService.xamlx en el diseñador y elimine las actividades **ReceiveRequest** y `SendReply` existentes; a continuación, arrastre una actividad `ReceiveAndSendReply` a la actividad de secuencia existente.  
  
    1.  Configure **OperationName** en UpperCaseString.  
  
    2.  Configure **ServiceContractName** en IUpperCaseString.  
  
    3.  Seleccione el cuadro de diálogo **CanCreateInstance**.  
  
3.  Seleccione la actividad SequentialService y, a continuación, haga clic en la pestaña **Variables** en la parte inferior del diseñador.Cree tres nuevas variables denominadas que StringToUpper, StringToReverse y StringToReturn de tipo String.  
  
4.  Haga clic en el vínculo **Definir** en la actividad **Receive**.Haga clic en **Parámetros** y cree un parámetro denominado InputString de tipo String que se asigne a StringToUpper.  
  
5.  Haga clic en el vínculo **Definir** en la actividad **SendReplyToReceive**.Haga clic en **Parámetros** y cree un parámetro denominado ModifiedString del tipo String, asignado a StringToReturn.  
  
6.  Para implementar la lógica para el servicio, cree un nuevo método en la clase StringLibrary utilizando el siguiente código.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
  
    ```  
  
7.  Para llamar al método UpperCaseString en la entrada, arrastre una actividad **InvokeMethod** desde el cuadro de herramientas hasta el espacio entre las actividades **Receive** y **SendReply**.Establezca las propiedades de la actividad de la manera siguiente:  
  
    1.  **MethodName**: UpperCaseString  
  
    2.  **Resultado**: StringToReverse  
  
    3.  **Parámetros**: cree un nuevo parámetro con una **Dirección** de In, un **Tipo** de String y un **Valor** de StringToUpper.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  Llamaremos ahora al primer servicio en la cadena modificada.Haga clic con el botón secundario en el proyecto y seleccione **Agregar referencia de servicio**.Agregue una referencia de servicio al servicio enhttp:\/\/localhost\/NestedServices\/StringReverserService.xamlx y compile el proyecto para crear una actividad personalizada para tener acceso al primer servicio web.  
  
9. Arrastre una instancia de la nueva actividad al flujo de trabajo, entre la actividad **InvokeMethod** y las actividades **SendReplyToReceive**.Asigne la variable StringToReverse a la propiedad InputString de la nueva actividad y la variable StringToReturn a la propiedad StringToReturn.  
  
10. Abra la página Propiedades para el proyecto NestedServices y cambie la **Página específica** de la pestaña **Web** a UpperCaserService.xamlx.  
  
11. Compruebe el servicio presionando F5.En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString\(\).En el panel Solicitud, escriba `Ejemplo` para el valor del parámetro InputString.Haga clic en **Invocar**.El servicio debería devolver "ELPMAS".  
  
### Crear un cliente para que llame al servicio  
  
1.  Agregue un nuevo proyecto de aplicación de consola llamado Cliente a la solución.  
  
2.  Haga clic con el botón secundario en el proyecto Cliente y, a continuación, seleccione **Agregar referencia de servicio**.En la ventana que aparece, haga clic en **Detectar**.Seleccione StringReverserService.xamlx y escriba ReverseService como el espacio de nombres.Haga clic en **Aceptar**.  
  
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