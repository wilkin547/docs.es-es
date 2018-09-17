---
title: 'Cómo: Ver el contenido de un ensamblado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abe4c130fb5da49ed0f53c776e23dba8fb5b15f7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593015"
---
# <a name="how-to-view-assembly-contents"></a>Cómo: Ver el contenido de un ensamblado
Se puede usar [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un archivo. Si el archivo que se examina es un ensamblado, esta información puede incluir los atributos del ensamblado además de referencias a otros módulos y ensamblados. Esta información puede ser útil para determinar si un archivo es un ensamblado o forma parte de uno y si el archivo tiene referencias a otros módulos o ensamblados.  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a>Para mostrar el contenido de un ensamblado mediante Ildasm.exe  
  
1.  Escriba **ildasm** \<*nombre de ensamblado*> en el símbolo del sistema. Por ejemplo, el comando siguiente desensambla el ensamblado `Hello.exe`.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a>Para ver información del manifiesto del ensamblado  
  
1.  Haga doble clic en el icono del manifiesto en la ventana del Desensamblador de MSIL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se inicia con un programa básico "Hello, World". Después de compilar el programa, use Ildasm.exe para desensamblar el ensamblado Hello.exe y ver el manifiesto del ensamblado.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Al ejecutar el comando ildasm.exe en el ensamblado Hello.exe y hacer doble clic en el icono del manifiesto en la ventana IL DASM se produce lo siguiente:  
  
```  
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 En la tabla siguiente se explica cada directiva del manifiesto del ensamblado Hello.exe usado en el ejemplo.  
  
|Directiva|Descripción|  
|---------------|-----------------|  
|**.assembly extern \<** *nombre del ensamblado* **>**|Especifica otro ensamblado que contiene elementos a los que hace referencia el módulo actual (en este ejemplo, `mscorlib`).|  
|**.publickeytoken \<** *token* **>**|Especifica el token de la clave real del ensamblado al que se hace referencia.|  
|**.ver \<** *número de versión* **>**|Especifica el número de versión del ensamblado al que se hace referencia.|  
|**.assembly \<** *nombre del ensamblado* **>**|Especifica el nombre del ensamblado.|  
|**.hash algorithm \<** *valor int32* **>**|Especifica el algoritmo hash usado.|  
|**.ver \<** *número de versión* **>**|Especifica el número de versión del ensamblado.|  
|**.module \<** *nombre del archivo* **>**|Especifica el nombre de los módulos que componen el ensamblado. En este ejemplo, el ensamblado consta de un único archivo.|  
|**.subsystem \<** *valor* **>**|Especifica el entorno de aplicación necesario para el programa. En este ejemplo, el valor 3 indica que este ejecutable se ejecuta desde una consola.|  
|**.corflags**|De momento, un campo reservado de los metadatos.|  
  
 Un manifiesto de ensamblado puede contener varias directivas diferentes, según el contenido del ensamblado. Para obtener una lista completa de las directivas del manifiesto del ensamblado, vea la documentación de ECMA, especialmente "Partition II: Metadata Definition and Semantics (Partición II: definición y semántica de los metadatos)" y "Partition III: CIL Instruction Set (Partición III: conjunto de instrucciones CIL)". La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.  
  
## <a name="see-also"></a>Vea también  
 [Dominios de aplicación y ensamblados](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)  
 [Temas "Cómo..." sobre dominios de aplicación y ensamblados](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
