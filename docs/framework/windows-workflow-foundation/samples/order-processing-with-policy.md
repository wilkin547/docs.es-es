---
title: Procesar pedidos con directiva
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6202d17741c276c03e80cedd979cbcf2f39ccc1f
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="order-processing-with-policy"></a>Procesar pedidos con directiva
El ejemplo de directiva de procesamiento de orden muestra algunas de las características clave introducidas en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] de Windows Workflow Foundation (WF). La funcionalidad siguiente es nueva para el motor de reglas de WF:  
  
-   Admisión de sobrecarga del operador.  
  
-   Compatibilidad para el operador `new`, permitiendo a los usuarios crear nuevos objetos y matrices a partir de las reglas de WF.  
  
-   Compatibilidad para los métodos de extensión para que el usuario experimente llamando a métodos de extensión desde las reglas de WF compatibles con los estilos de codificación C#.  
  
> [!NOTE]
>  Este ejemplo necesita que [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] esté instalado para compilarse y ejecutarse. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] es necesario para abrir los archivos de proyecto y de solución.  
  
 El ejemplo muestra un proyecto `OrderProcessingPolicy` donde se introduce una orden de cliente, que está compuesta de una lista numerada de elementos disponibles, y un código postal. La orden se procesa correctamente si ambas entradas son correctas; de lo contrario, la directiva crea los objetos de error, utilizando un operador `+` sobrecargado y un método de extensión predefinido para informar al usuario de los errores.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]métodos de extensión, vea [C# versión 3.0 especificación](http://go.microsoft.com/fwlink/?LinkId=95402).  
  
 El ejemplo consta de los proyectos siguientes:  
  
-   `OrderErrorLibrary`  
  
     `OrderErrorLibrary` es una biblioteca de clases que define las clases `OrderError` y `OrderErrorCollection`. Se crea una instancia `OrderError` cuando se escribe una entrada no válida. La biblioteca también proporciona un método de extensión en la clase `OrderErrorCollection` que genera la propiedad `ErrorText` en todos los objetos `OrderError` en `OrderErrorCollection`.  
  
-   `OrderProcessingPolicy`  
  
     El proyecto `OrderProcessingPolicy` es una aplicación de consola de WF que define una actividad `PolicyFromFile` única. La actividad tiene las siguientes reglas:  
  
    -   `invalidItemNum`  
  
         Esta regla valida que el número del elemento esté entre 1 y 6, incluido. Si el número del elemento está dentro del intervalo válido, la regla no hace nada (excepto imprimir en la consola). Si el número del elemento no está entre 1 y 6, la regla `invalidItemNum` hace lo siguiente:  
  
        1.  Crea un nuevo objeto `OrderError`, pasándole el número del elemento introducido y establece las propiedades `ErrorText` y `CustomerName` en el objeto.  
  
        2.  Crea un objeto `invalidItemNumErrorCollection`.  
  
        3.  Agrega la instancia creada recientemente `OrderError` a `invalidItemNumErrorCollection`.  
  
         Esto muestra la compatibilidad para el operador `new`, con el que puede crear instancias de los objetos dentro de las reglas.  
  
    -   `invalidZip`  
  
         Esta regla valida que el código postal tiene 5 dígitos y que se sitúa dentro del intervalo 600 a 99998. Si el código postal está dentro del intervalo válido, la regla no hace nada (excepto imprimir en la consola). Si la longitud del código postal es menor que 5 o el código postal no está entre 00600 y 99998, la regla `invalidZip` hace lo siguiente:  
  
        1.  Crea un objeto `OrderError`, pasándole el código postal introducido y establece las propiedades `ErrorText` y l`CustomerName` en el objeto.  
  
        2.  Crea un objeto `invalidZipCodeErrorCollection`.  
  
        3.  Agrega la instancia creada recientemente `OrderError` a la `invalidZipCodeErrorCollection` creada recientemente.  
  
         Esta regla muestra de nuevo la compatibilidad para el operador `new`, que le permite crear instancias de los objetos dentro de las reglas.  
  
    -   `displayErrors`  
  
         Esta regla comprueba si las dos reglas anteriores han agregado errores en los dos objetos `OrderErrorCollection``invalidItemNumErrorCollection` y `invalidIZipCodeErrorCollection`. Si hay errores ( `invalidItemNumErrorCollection` o `invalidZipCodeErrorCollection` no es `null`), la regla hace lo siguiente:  
  
        1.  Llama a sobrecargado `+` operador que se va a copiar el contenido de `invalidItemNumErrorCollection` y `invalidZipCodeErrorCollection` a una `invalidOrdersCollection``OrderErrorCollection` instancia.  
  
        2.  Llama al método de extensión `PrintOrderErrors` en `invalidOrdersCollection` y genera la propiedad `ErrorText` en todos los objetos `orderError` en `invalidOrdersCollection`.  
  
 El operador `+` sobrecargado en `OrderErrorCollection` se define en la clase `OrderErrorCollection`, en el proyecto `OrderErrorLibrary`. Toma dos objetos `OrderErrorCollection` y los combina en un objeto `OrderErrorCollection`.  
  
 El método de extensión `PrintOrderErrors` también se define en el proyecto `OrderErrorLibrary`. Los métodos de extensión son una nueva característica de C# que permite a los programadores agregar nuevos métodos al contrato público de un tipo CLR existente, sin tener que derivar una clase del mismo o recompilar el tipo original.  
  
 Al ejecutar el ejemplo se le pide que escriba un nombre, el número del elemento del elemento que se va a comprar y un código postal. Las reglas definidas en la actividad de directiva comprueban a continuación esta información. A continuación, puede ver un resultado de ejemplo del programa.  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra el archivo de proyecto OrderProcessingPolicy.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Hay dos proyectos diferentes en la solución: `OrderErrorLibrary` y `OrderProcessingPolicy`. El proyecto `OrderProcessingPolicy` utiliza clases y métodos definidos en `OrderErrorLibrary`.  
  
3.  Compile todos los proyectos.  
  
4.  Haga clic en **ejecutar**.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`