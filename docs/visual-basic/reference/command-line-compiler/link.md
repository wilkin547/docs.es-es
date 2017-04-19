---
title: /Link (Visual Basic) | Documentos de Microsoft
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
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: e98c855f0a0185e9d1b6682df9fc734e9f1f07bc
ms.lasthandoff: 03/13/2017

---
# <a name="link-visual-basic"></a>/link (Visual Basic)
Hace que el compilador disponer de información de tipos COM en los ensamblados especificados al proyecto que se está compilando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileList`|Obligatorio. Lista delimitada por comas de nombres de archivo de ensamblado. Si el nombre de archivo contiene un espacio, encierre el nombre entre comillas.|  
  
## <a name="remarks"></a>Comentarios  
 El `/link` opción le permite implementar una aplicación que contiene información de tipo incrustada. La aplicación puede utilizar tipos en un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución. Si se publican varias versiones del ensamblado en tiempo de ejecución, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar. Para obtener un ejemplo, vea [Tutorial: incrustar los tipos de ensamblados administrados](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 Mediante el `/link` opción es especialmente útil cuando se trabaja con la interoperabilidad COM. Puede incrustar tipos COM para que la aplicación ya no requiere un ensamblado de interoperabilidad primario (PIA) en el equipo de destino. El `/link` opción indica al compilador que incruste la información de tipo COM desde el ensamblado de interoperabilidad que se hace referencia en el código compilado resultante. El tipo COM se identifica mediante el valor de CLSID (GUID). Como resultado, puede ejecutar la aplicación en un equipo de destino que ha instalado a los mismos tipos COM con los mismos valores CLSID. Aplicaciones que automatizan Microsoft Office son un buen ejemplo. Dado que las aplicaciones como Office suelen mantener el mismo valor CLSID en las distintas versiones, la aplicación puede usar los tipos COM que se hace referencia como larga como .NET Framework 4 o posterior está instalado en el equipo de destino y la aplicación utiliza métodos, propiedades o eventos que se incluyen en los tipos COM que se hace referencia.  
  
 El `/link` opción incrusta sólo interfaces, estructuras y delegados. No se admite la incrustación de clases COM.  
  
> [!NOTE]
>  Cuando crea una instancia de un tipo COM incrustado en el código, debe crear la instancia mediante la interfaz adecuada. Al intentar crear una instancia de un tipo COM incrustado mediante el uso de la coclase, produce un error.  
  
 Para establecer el `/link` opción [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], agregue una referencia de ensamblado y establezca el `Embed Interop Types` propiedad **true**. El valor predeterminado para la `Embed Interop Types` propiedad es **false**.  
  
 Si vincula a un ensamblado COM (ensamblado A) que hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes acciones:  
  
-   Un tipo en el ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
-   Se invoca un campo, propiedad, evento o un método que tiene un tipo de parámetro o tipo de valor devuelto del ensamblado B.  
  
 Utilice [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.  
  
 Como el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador, el `/link` opción del compilador usa el archivo de respuesta Vbc.rsp, que las referencias se utilizan con frecuencia [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados. Utilice la [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) opción del compilador si no desea que el compilador use el archivo Vbc.rsp.  
  
 La forma abreviada de `/link` es `/l`.  
  
## <a name="generics-and-embedded-types"></a>Tipos incrustados y genéricos  
 Las secciones siguientes describen las limitaciones al usar tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.  
  
### <a name="generic-interfaces"></a>Interfaces genéricas  
 No se puede usar interfaces genéricas que se incrustan desde un ensamblado de interoperabilidad. Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-vb[1 VbLinkCompiler](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a>Tipos de parámetros genéricos  
 Tipos que tienen un parámetro genérico cuyo tipo se incrusta desde un ensamblado de interoperabilidad no pueden usarse si dicho tipo pertenece a un ensamblado externo. Esta restricción no se aplica a las interfaces. Por ejemplo, considere el <xref:Microsoft.Office.Interop.Excel.Range>interfaz que se define en la <xref:Microsoft.Office.Interop.Excel>ensamblado.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range> Si incrusta de una biblioteca de tipos de interoperabilidad de la <xref:Microsoft.Office.Interop.Excel>ensamblado y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es el <xref:Microsoft.Office.Interop.Excel.Range>de la interfaz, que método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel>  
  
 [!code-vb[VbLinkCompiler&#2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler Nº&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve el <xref:System.Collections.IList>interfaz genérica sin errores.</xref:System.Collections.IList>  
  
 [!code-vb[VbLinkCompiler&#5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila el archivo de código fuente `OfficeApp.vb` y hacer referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para producir `OfficeApp.exe`.  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Tutorial: Incrustar los tipos de los ensamblados administrados](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Introducción a la interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
