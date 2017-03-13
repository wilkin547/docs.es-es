---
title: "C&#243;mo: Hacer referencia a objetos COM desde Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interoperabilidad COM, hacer referencia a objetos COM"
  - "objetos COM, hacer referencia"
  - "ensamblados de interoperabilidad"
  - "objetos [Visual Basic], hacer referencia"
  - "hacer referencia a objetos, objetos COM de Visual Basic"
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Hacer referencia a objetos COM desde Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], para agregar referencias a objetos COM que tienen bibliotecas de tipos, es preciso crear un ensamblado de interoperabilidad para la biblioteca COM.  Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y después se reenvían al objeto COM real.  Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a la aplicación de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
 Se puede hacer referencia a un objeto COM sin usar un ensamblado de interoperabilidad si se incrusta la información de tipo del objeto COM en un ensamblado de .NET.  Para incrustar la información de tipo, establezca la propiedad `Embed Interop Types` en `True` para la referencia al objeto COM.  Si compila mediante el compilador de línea de comandos, use la opción `/link` para hacer referencia a la biblioteca COM.  Para obtener más información, vea [\/link](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] crea automáticamente ensamblados de interoperabilidad cuando se agrega una referencia a una biblioteca de tipos en el entorno de desarrollo integrado \(IDE\).  Si trabaja desde la línea de comandos, puede utilizar la herramienta Tlbimp para crear manualmente ensamblados de interoperabilidad.  
  
### Para agregar referencias a objetos COM  
  
1.  En el menú **Proyecto**, haga clic en **Agregar referencia** y, a continuación, elija la ficha **COM** en el cuadro de diálogo.  
  
2.  Seleccione en la lista de objetos COM el componente que desea utilizar.  
  
3.  Para simplificar el acceso al ensamblado de interoperabilidad, agregue una instrucción `Imports` al principio del código de la clase o el módulo en el que va a utilizar el objeto COM:  Por ejemplo, en el siguiente ejemplo de código se importa el espacio de nombres `INKEDLib` de los objetos a los que se hace referencia en la biblioteca `Microsoft InkEdit Control 1.0`.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### Para crear un ensamblado de interoperabilidad mediante Tlbimp  
  
1.  Agregue la ubicación de Tlbimp a la ruta de búsqueda, si no forma parte ya de la ruta de búsqueda y si no está actualmente en el directorio en que se encuentra.  
  
2.  Llame a Tlbimp desde el símbolo del sistema con la siguiente información:  
  
    -   Nombre y ubicación del archivo DLL que contiene la biblioteca de tipos  
  
    -   Nombre y ubicación del espacio de nombres en que debe colocarse la información  
  
    -   Nombre y ubicación del ensamblado de interoperabilidad de destino  
  
     El código siguiente proporciona un ejemplo:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Puede utilizar Tlbimp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para objetos COM no registrados.  Sin embargo, los objetos COM a los que se hace referencia mediante ensamblados de interoperabilidad deben registrarse correctamente en el equipo en que se vayan a utilizar.  Puede registrar un objeto COM con la herramienta Regsvr32 incluida en el sistema operativo Windows.  
  
## Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)