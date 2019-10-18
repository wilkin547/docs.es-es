---
title: 'Cómo: Hacer referencia a objetos COM desde Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: ea0e1d9b0ae9f151d901c425512508ba7bc05343
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524362"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Cómo: Hacer referencia a objetos COM desde Visual Basic
En Visual Basic, la adición de referencias a objetos COM que tienen bibliotecas de tipos requiere la creación de un ensamblado de interoperabilidad para la biblioteca COM. Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real. Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a la aplicación .NET Framework.  
  
 Puede hacer referencia a un objeto COM sin utilizar un ensamblado de interoperabilidad incrustando la información de tipo para el objeto COM en un ensamblado .NET. Para insertar información de tipo, establezca la propiedad `Embed Interop Types` en `True` para la referencia al objeto COM. Si va a compilar mediante el compilador de línea de comandos, utilice la opción `/link` para hacer referencia a la biblioteca COM. Para obtener más información, vea [-Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic crea automáticamente ensamblados de interoperabilidad al agregar una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE). Al trabajar desde la línea de comandos, puede usar la utilidad TlbImp para crear manualmente ensamblados de interoperabilidad.  
  
### <a name="to-add-references-to-com-objects"></a>Para agregar referencias a objetos COM  
  
1. En el menú **proyecto** , elija **Agregar referencia** y, a continuación, haga clic en la pestaña **com** del cuadro de diálogo.  
  
2. Seleccione el componente que desea usar en la lista de objetos COM.  
  
3. Para simplificar el acceso al ensamblado de interoperabilidad, agregue una instrucción `Imports` a la parte superior de la clase o módulo en el que va a usar el objeto COM. Por ejemplo, en el ejemplo de código siguiente se importa el espacio de nombres `INKEDLib` para los objetos a los que se hace referencia en la biblioteca de `Microsoft InkEdit Control 1.0`.  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Para crear un ensamblado de interoperabilidad mediante Tlbimp  
  
1. Agregue la ubicación de Tlbimp a la ruta de búsqueda, si aún no forma parte de la ruta de acceso de búsqueda y no está actualmente en el directorio donde se encuentra.  
  
2. Llame a Tlbimp desde un símbolo del sistema y proporcione la siguiente información:  
  
    - Nombre y ubicación de la DLL que contiene la biblioteca de tipos  
  
    - Nombre y ubicación del espacio de nombres donde se debe colocar la información  
  
    - Nombre y ubicación del ensamblado de interoperabilidad de destino  
  
     El siguiente fragmento de código muestra un ejemplo:  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Puede usar TlbImp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para objetos COM no registrados. Sin embargo, los objetos COM a los que hacen referencia los ensamblados de interoperabilidad deben estar registrados correctamente en el equipo en el que se van a utilizar. Puede registrar un objeto COM mediante la utilidad regsvr32 incluida en el sistema operativo Windows.  
  
## <a name="see-also"></a>Vea también

- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Tutorial: Implementación de la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
