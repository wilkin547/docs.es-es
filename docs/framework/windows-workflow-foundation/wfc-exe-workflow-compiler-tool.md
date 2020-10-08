---
title: Wfc.exe (herramienta de compilador de línea de comandos de flujo de trabajo)
description: Comprenda wfc.exe, la herramienta de compilador de línea de comandos del flujo de trabajo.
ms.date: 10/10/2020
helpviewer_keywords:
- wfc [Workflow]
- compiler tool
- wfc.exe
- Workflow, compilation
- Workflow, XOML files
- Workflow, wcf
ms.openlocfilehash: cf89962014584adf098118044b063b38b29160b7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844617"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a>wfc.exe (herramienta de compilador de línea de comandos de flujo de trabajo)
> [!NOTE]
> En esta documentación se describen los tipos y espacios de nombres que están obsoletos.

La herramienta de compilador de línea de comandos de wfc.exe Workflow funciona con archivos de marcado de flujo de trabajo antiguos que tienen la extensión de archivo *. xoml* (obsoleto).

## <a name="compilation-process"></a>Proceso de compilación

Cuando se compilan los flujos de trabajo, se llevan a cabo los procedimientos siguientes como parte del proceso de compilación:

- La validación se realiza con el fin de asegurarse de que para las actividades de flujo de trabajo se validan basándose en las reglas que las actividades han establecido para sí mismas. Si hay errores de validación, el compilador devuelve una lista.  
- Se genera una clase parcial a partir de la definición de marcado que se introduce en el compilador.  

- El código se genera para ayudar en la ejecución del motor de tiempo de ejecución de las actividades. Se generan suscripciones a los eventos, que ayudan a las actividades a saber cuándo ha finalizado la ejecución de las actividades que contienen.  
- Las clases parciales generadas a partir del archivo de marcado y las clases parciales del archivo de código se introducen en el compilador de .NET Framework C# o Visual Basic. El resultado de este proceso es el ensamblado de .NET, WorkflowSample.dll. Se puede implementar para ejecutar el flujo de trabajo.

### <a name="compiler-options"></a>Opciones del compilador

En esta sección se muestran las opciones del compilador de línea de comandos de wfc.exe Workflow.

```output
    Microsoft (R) Windows Workflow Compiler version 3.0.0.0
    Copyright (C) Microsoft Corporation 2005. All rights reserved.

                      Windows Workflow Compiler Options

    wfc.exe <Xoml file list> /target:assembly [<vb/cs file list>] [/language:...]
            [/out:...] [/reference:...] [/library:...] [/debug...] [/nocode...]
             [/checktypes...] [/resource:<resource info>]

                            - OUTPUT FILE -
    /out:<file>             Output file name
    /target:assembly        Build a Windows Workflow assembly (default).
                            Short form: /t:assembly
    /target:exe             Build a Windows Workflow application.
                            Short form: /t:exe
    /delaysign[+|-]         Delay-sign the assembly using only the public portion
                            of the strong name key.
    /keyfile:<file>         Specifies a strong name key file.
    /keycontainer:<string>  Specifies a strong name key container.

                            - INPUT FILES -
    <Xoml file list>        Xoml source file name(s).
    <vb/cs file list>       Code-beside file name(s).
    /reference:<file list>  Reference metadata from the specified assembly file(s).
                            Short form is '/r:'.
    /library:<path list>    Set of directories where to lookup for the references.
                            Short form is '/lib:'.
    /resource:<resinfo>     Embed the specified resource. Short form is '/res:'.
                            resinfo format is <file>[,<name>[,public|private]].

    Rules and freeform layout files must be embedded as assembly resources.
    The resource name is constructed by using the namespace and type name
    of the activity. For example, an activity named "MyActivity" in namespace
    "WFProject" would require resource names "WFProject.MyActivity.rules"
    and/or "WFProject.MyActivity.layout".

                            - CODE GENERATION -
    /debug[+|-]             Emit full debugging information. The default is '+'.
    /nocode[+|-]            Disallow code-beside model.
                            The default is '-'. Short form is '/nc:'.
    /checktypes[+|-]        Check for permitted types in wfc.exe.config file.
                            The default is '-'. Short form is '/ct:'.

                            - LANGUAGE -
    /language:[cs|vb]       The language to use for the generated class.
                            The default is 'CS' (C#). Short form is '/l:'.
    /rootnamespace:<string> Specifies the root Namespace for all type declarations.
                            Valid only for 'VB' (Visual Basic) language.
                            Short form is '/rns:'.

                            - MISCELLANEOUS -
    /help                   Display this usage message. Short form is '/?'.
    /nologo                 Suppress compiler copyright message. Short form is '/n'.

    /nowarn                 Ignore compiler warnings. Short form is '/w'.
```

## <a name="remarks"></a>Observaciones
> [!NOTE]
> En esta documentación se describen los tipos y espacios de nombres que están obsoletos.

Normalmente, en el archivo *wfc.exe.config* se define una lista de tipos autorizados. Durante la fase de validación de la compilación del flujo de trabajo, se rechaza un documento de origen del flujo de trabajo si éste o el archivo de reglas complementario hacen referencia directamente a cualquier tipo de .NET Framework que no esté presente en una lista de tipos autorizados. La lista de tipos autorizados es un documento XML donde cada entrada indica un `Assembly` , un `Namespace` , un `TypeName` y un `True` indicador {&#124;`False` } autorizado. `AuthorizedType` corresponde a una entrada de la lista. Se permiten las designaciones de caracteres comodín, que se pueden usar para incluir o excluir espacios de nombres completos. Por ejemplo, `Type="System.*"` incluye todos los tipos en <xref:System> , incluidos los tipos contenidos en los espacios de nombres secundarios.
  
El uso de una lista de tipos autorizados se controla mediante la <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> opción `'/checktypes'` .

```xml  
<configuration>  
  <System.Workflow.ComponentModel.WorkflowCompiler>
    <authorizedTypes>
      <targetFx version="v4.0">
        ...
        <authorizedType Assembly="System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True"/>
        ...
      </targetFx>
    </authorizedTypes>
  </System.Workflow.ComponentModel.WorkflowCompiler>  
</configuration>  
```

> [!WARNING]
> Cuando el `Type="System.*"` tipo está presente, es posible incluir otros tipos no deseados, como `Type="System.Configuration"` , para la compilación. Tenga cuidado y revise cada uno de ellos. Para cualquier tipo que se deba restringir, asegúrese de establecer `Authorized` en `False` .

## <a name="see-also"></a>Vea también

- [Clase AuthorizedType](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
