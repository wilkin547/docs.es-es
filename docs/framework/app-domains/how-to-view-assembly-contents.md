---
title: "C&#243;mo: Ver el contenido de un ensamblado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "manifiesto del ensamblado, ver información"
  - "Ildasm.exe"
  - "Desensamblador de MSIL"
  - "ensamblados [.NET Framework], ver contenido"
  - "ver información de ensamblados"
  - "MSIL"
  - "ver información de MSIL"
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Ver el contenido de un ensamblado
El [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) se puede usar para ver la información del lenguaje intermedio de Microsoft \(MSIL\) de un archivo.  Si el archivo que se examina es un ensamblado, esta información puede incluir los atributos de dicho ensamblado, así como referencias a otros módulos y ensamblados.  Esta información puede resultar útil para determinar si el archivo es un ensamblado o parte de un ensamblado y si tiene referencias a otros módulos o ensamblados.  
  
### Para mostrar el contenido de un ensamblado mediante Ildasm.exe  
  
1.  *Nombre del ensamblado*de \<**ildasm** de tipo\> en el símbolo del sistema.  Por ejemplo, con el comando siguiente se desensambla el ensamblado `Hello.exe`.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### Para ver información de manifiesto del ensamblado  
  
1.  Haga doble clic en el icono del MANIFIESTO en la ventana del Desensamblador MSIL.  
  
## Ejemplo  
 El siguiente ejemplo empieza con un programa básico "Hola a todos".  Después de compilar el programa, utilice Ildasm.exe para desensamblar el ensamblado Hello.exe y ver el manifiesto del ensamblado.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 La ejecución del comando ildasm.exe en el ensamblado Hello.exe y un doble clic en el icono del MANIFIESTO en la ventana de IL DASM generan el resultado siguiente:  
  
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
  
 En la siguiente tabla se describen las directivas del manifiesto del ensamblado Hello.exe utilizado en el ejemplo.  
  
|Directiva|Descripción|  
|---------------|-----------------|  
|*nombre del ensamblado* **\>**de**.assembly extern \<**|Especifica otro ensamblado que contiene elementos a los que hace referencia el módulo actual \(en este ejemplo, `mscorlib`\).|  
|*símbolo* **\>**de **.publickeytoken \<**|Especifica el token de la clave real del ensamblado al que se hace referencia.|  
|*número de versión* **\>**de **.ver \<**|Especifica el número de versión del ensamblado al que se hace referencia.|  
|*nombre del ensamblado* **\>**de**.assembly \<**|Especifica el nombre del ensamblado.|  
|**.hash algorithm \<** *valor int32* **\>**|Especifica el algoritmo de hash utilizado.|  
|*número de versión* **\>**de **.ver \<**|Especifica el número de versión del ensamblado.|  
|*nombre de archivo* **\>**de**.module \<**|Especifica el nombre de los módulos que forman el ensamblado.  En este ejemplo, el ensamblado sólo tiene un archivo.|  
|*valor* **\>**de**.subsystem \<**|Especifica el entorno de aplicación que requiere el programa.  En este ejemplo, el valor 3 indica que este ejecutable se ejecuta desde una consola.|  
|**.corflags**|En la actualidad, un campo reservado de los metadatos.|  
  
 Un manifiesto del ensamblado puede contener varias directivas distintas, dependiendo del contenido del ensamblado.  Para obtener una lista completa de las directivas del manifiesto del ensamblado, consulte la documentación \(en inglés\) de ECMA, especialmente la partición II, sobre definición y semántica de metadatos, y la partición III, sobre el conjunto de instrucciones de CIL.  La documentación está disponible en línea; consulte [ECMA C\# y estándares de Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) MSDN y [Estándar ECMA\-335 \- Common Language Infrastructure \(CLI\)](http://go.microsoft.com/fwlink/?LinkID=65552) en el sitio Web de ECMA International.  
  
## Vea también  
 [Application Domains and Assemblies](http://msdn.microsoft.com/es-es/433b04ae-4ba8-4849-9dbd-79194f240346)   
 [Temas "Cómo..." sobre dominios de aplicación y ensamblados](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)   
 [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)