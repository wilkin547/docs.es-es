---
title: 'Cómo: Hacer referencia a objetos COM desde Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f6f7b4887e2cfba65da7a7a890b78c3d6a8508f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Cómo: Hacer referencia a objetos COM desde Visual Basic
En Visual Basic, al agregar referencias a objetos COM que tienen bibliotecas de tipos, requiere la creación de un ensamblado de interoperabilidad para la biblioteca COM. Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real. Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y reenvían a su [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación.  
  
 Puede hacer referencia a un objeto COM sin usar un ensamblado de interoperabilidad incrustando la información de tipo para el objeto COM en un ensamblado. NET. Para incrustar información de tipo, establezca el `Embed Interop Types` propiedad `True` para la referencia al objeto COM. Si realiza la compilación mediante el compilador de línea de comandos, use el `/link` opción para hacer referencia a la biblioteca COM. Para obtener más información, consulte [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic crea automáticamente ensamblados de interoperabilidad cuando se agrega una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE). Cuando se trabaja desde la línea de comandos, puede utilizar la utilidad Tlbimp para crear manualmente los ensamblados de interoperabilidad.  
  
### <a name="to-add-references-to-com-objects"></a>Para agregar referencias a objetos COM  
  
1.  En el **proyecto** menú, elija **Agregar referencia** y, a continuación, haga clic en el **COM** ficha en el cuadro de diálogo.  
  
2.  Seleccione el componente que desea usar en la lista de objetos COM.  
  
3.  Para simplificar el acceso al ensamblado de interoperabilidad, agregue un `Imports` instrucción a la parte superior de la clase o módulo en el que va a utilizar el objeto COM. Por ejemplo, en el ejemplo de código siguiente se importa el espacio de nombres `INKEDLib` para los objetos que se hace referencia en el `Microsoft InkEdit Control 1.0` biblioteca.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Para crear un ensamblado de interoperabilidad mediante Tlbimp  
  
1.  Agregue la ubicación de Tlbimp a la ruta de acceso de búsqueda, si ya no forme parte de la ruta de acceso de búsqueda y no está actualmente en el directorio donde se encuentra.  
  
2.  Llame a Tlbimp desde un símbolo del sistema, con la siguiente información:  
  
    -   Nombre y la ubicación del archivo DLL que contiene la biblioteca de tipos  
  
    -   Nombre y ubicación del espacio de nombres donde se debe colocar la información  
  
    -   Nombre y la ubicación del ensamblado de interoperabilidad de destino  
  
     El siguiente fragmento de código muestra un ejemplo:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Puede utilizar Tlbimp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para los objetos COM no registrados. Sin embargo, los objetos COM que hace referencia a ensamblados de interoperabilidad deben registrarse correctamente en el equipo donde se van a usarse. Puede registrar un objeto COM mediante la utilidad Regsvr32 incluida con el sistema operativo Windows.  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (Exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Tutorial: Implementación de la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
