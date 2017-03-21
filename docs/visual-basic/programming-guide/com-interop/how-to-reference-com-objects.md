---
title: "Cómo: hacer referencia a objetos COM desde Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 97c132bcbd36ba7810acadb2aebddc5e84f0b44d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Cómo: Hacer referencia a objetos COM desde Visual Basic
En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], agregar referencias a objetos COM que tienen bibliotecas de tipos, requiere la creación de un ensamblado de interoperabilidad para la biblioteca COM. Referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real. Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a su [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicación.  
  
 Para hacer referencia a un objeto COM sin usar un ensamblado de interoperabilidad incrustar la información de tipo para el objeto COM en un ensamblado. NET. Para incrustar información de tipo, establezca el `Embed Interop Types` propiedad `True` para la referencia al objeto COM. Si se compila con el compilador de línea de comandos, use el `/link` opción para hacer referencia a la biblioteca COM. Para obtener más información, consulte [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]crea automáticamente ensamblados de interoperabilidad cuando se agrega una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE). Cuando se trabaja desde la línea de comandos, puede utilizar la utilidad Tlbimp para crear manualmente ensamblados de interoperabilidad.  
  
### <a name="to-add-references-to-com-objects"></a>Para agregar referencias a objetos COM  
  
1.  En el **proyecto** menú, elija **Agregar referencia** y, a continuación, haga clic en el **COM** ficha en el cuadro de diálogo.  
  
2.  Seleccione el componente que desea utilizar en la lista de objetos COM.  
  
3.  Para simplificar el acceso al ensamblado de interoperabilidad, agregue un `Imports` en la parte superior de la clase o módulo en el que va a utilizar el objeto COM. Por ejemplo, en el ejemplo de código siguiente se importa el espacio de nombres `INKEDLib` para los objetos que se hace referenciados en el `Microsoft InkEdit Control 1.0` biblioteca.  
  
     [!code-vb[VbVbalrInterop Nº&40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Para crear un ensamblado de interoperabilidad mediante Tlbimp  
  
1.  Agregue la ubicación de Tlbimp a la ruta de búsqueda, si ya no es parte de la ruta de búsqueda y no está actualmente en el directorio donde se encuentra.  
  
2.  Llame a Tlbimp desde el símbolo del sistema, con la siguiente información:  
  
    -   Nombre y ubicación de la DLL que contiene la biblioteca de tipos  
  
    -   Nombre y ubicación del espacio de nombres donde se debe colocar la información  
  
    -   Nombre y ubicación del ensamblado de interoperabilidad de destino  
  
     El siguiente fragmento de código muestra un ejemplo:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Puede utilizar Tlbimp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para objetos COM no registrados. Sin embargo, los objetos COM al que hace referencia a ensamblados de interoperabilidad deben registrarse correctamente en el equipo donde se van a utilizar. Puede registrar un objeto COM mediante la herramienta Regsvr32 incluida con el sistema operativo Windows.  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Solucionar problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
