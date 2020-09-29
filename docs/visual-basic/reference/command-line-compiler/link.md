---
title: -link
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: 3c02c914a27e6095f8f6bc34e29e2447a1a373e5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065728"
---
# <a name="-link-visual-basic"></a>-link (Visual Basic)

Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-link:fileList  
```

o  

```console
-l:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileList`|Obligatorio. Lista delimitada por comas de nombres de archivos de ensamblado. Si el nombre de archivo contiene un espacio, escríbalo entre comillas.|  
  
## <a name="remarks"></a>Comentarios  

 La opción `-link` permite implementar una aplicación que tiene información de tipo incrustada. La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución. Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar. Para obtener un ejemplo, vea [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).  
  
 La opción `-link` resulta de especial utilidad cuando se trabaja con la interoperabilidad COM. Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino. La opción `-link` indica al compilador que incruste la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante. El tipo COM se identifica mediante el valor de CLSID (GUID). Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID. Las aplicaciones que automatizan Microsoft Office son un buen ejemplo. Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia.  
  
 La opción `-link` incrusta únicamente interfaces, estructuras y delegados. No se admite la incrustación de clases COM.  
  
> [!NOTE]
> Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada. Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.  
  
 Para establecer la opción `-link` en Visual Studio, agregue una referencia de ensamblado y establezca la propiedad `Embed Interop Types` en **true**. El valor predeterminado de la propiedad `Embed Interop Types` es **false**.  
  
 Si vincula a un ensamblado COM (ensamblado A) que a su vez hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes condiciones:  
  
- Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
- Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.  
  
 Use [-libpath](libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.  
  
 Como sucede con [-reference](reference.md), la opción del compilador `-link` usa el archivo de respuesta Vbc.rsp, que hace referencia a ensamblados de .NET Framework que se usan con frecuencia. Use la opción del compilador [-noconfig](noconfig.md) si no quiere que el compilador utilice el archivo Vbc.rsp.  
  
 La forma abreviada de `-link` es `-l`.  
  
## <a name="generics-and-embedded-types"></a>Tipos incrustados y genéricos  

 En las secciones siguientes se describen las limitaciones sobre el uso de tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.  
  
### <a name="generic-interfaces"></a>Interfaces genéricas  

 No se puede usar interfaces genéricas que se incrusten desde un ensamblado de interoperabilidad. Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a>Tipos que tienen parámetros genéricos  

 Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo. Esta restricción no se aplica a las interfaces. Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>. Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a>Ejemplo  

 En la línea de comandos siguiente se compila el archivo de código fuente `OfficeApp.vb` y se hace referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.  
  
```console  
vbc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Tutorial: Inserción de tipos de ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md)
- [-reference (Visual Basic)](reference.md)
- [-noconfig](noconfig.md)
- [-libpath](libpath.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Introducción a la interoperabilidad COM](../../programming-guide/com-interop/introduction-to-com-interop.md)
