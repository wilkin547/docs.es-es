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
ms.openlocfilehash: 43ba068663db9f8c3816a6f731395a6682a130e6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083298"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Cómo: Hacer referencia a objetos COM desde Visual Basic

En Visual Basic, la adición de referencias a objetos COM que tienen bibliotecas de tipos requiere la creación de un ensamblado de interoperabilidad para la biblioteca COM. Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real. Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a la aplicación .NET Framework.  
  
 Puede hacer referencia a un objeto COM sin utilizar un ensamblado de interoperabilidad incrustando la información de tipo para el objeto COM en un ensamblado .NET. Para insertar información de tipo, establezca la `Embed Interop Types` propiedad en `True` para la referencia al objeto com. Si va a compilar mediante el compilador de línea de comandos, use la `/link` opción para hacer referencia a la biblioteca com. Para obtener más información, vea [-Link (Visual Basic)](../../reference/command-line-compiler/link.md).  
  
 Visual Basic crea automáticamente ensamblados de interoperabilidad al agregar una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE). Al trabajar desde la línea de comandos, puede usar la utilidad TlbImp para crear manualmente ensamblados de interoperabilidad.  
  
### <a name="to-add-references-to-com-objects"></a>Para agregar referencias a objetos COM  
  
1. En el menú **proyecto** , elija **Agregar referencia** y, a continuación, haga clic en la pestaña **com** del cuadro de diálogo.  
  
2. Seleccione el componente que desea usar en la lista de objetos COM.  
  
3. Para simplificar el acceso al ensamblado de interoperabilidad, agregue una `Imports` instrucción a la parte superior de la clase o módulo en el que va a usar el objeto com. Por ejemplo, en el ejemplo de código siguiente se importa el espacio `INKEDLib` de nombres para los objetos a los que se hace referencia en la `Microsoft InkEdit Control 1.0` biblioteca.  
  
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

- [Interoperabilidad COM](index.md)
- [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Tutorial: Implementación de la herencia mediante objetos COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [Solución de problemas de interoperabilidad](troubleshooting-interoperability.md)
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
