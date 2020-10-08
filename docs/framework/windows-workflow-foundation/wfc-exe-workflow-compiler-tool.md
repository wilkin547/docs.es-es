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
# <a name="wfcexe-workflow-command-line-compiler-tool"></a><span data-ttu-id="72460-103">wfc.exe (herramienta de compilador de línea de comandos de flujo de trabajo)</span><span class="sxs-lookup"><span data-stu-id="72460-103">wfc.exe (Workflow Command-line Compiler Tool)</span></span>
> [!NOTE]
> <span data-ttu-id="72460-104">En esta documentación se describen los tipos y espacios de nombres que están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="72460-104">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="72460-105">La herramienta de compilador de línea de comandos de wfc.exe Workflow funciona con archivos de marcado de flujo de trabajo antiguos que tienen la extensión de archivo *. xoml* (obsoleto).</span><span class="sxs-lookup"><span data-stu-id="72460-105">The wfc.exe workflow command-line compiler tool works with old workflow markup files that have the file extension *.xoml* (obsoleted).</span></span>

## <a name="compilation-process"></a><span data-ttu-id="72460-106">Proceso de compilación</span><span class="sxs-lookup"><span data-stu-id="72460-106">Compilation process</span></span>

<span data-ttu-id="72460-107">Cuando se compilan los flujos de trabajo, se llevan a cabo los procedimientos siguientes como parte del proceso de compilación:</span><span class="sxs-lookup"><span data-stu-id="72460-107">When workflows are compiled, the following procedures are performed as part of the compilation process:</span></span>

- <span data-ttu-id="72460-108">La validación se realiza con el fin de asegurarse de que para las actividades de flujo de trabajo se validan basándose en las reglas que las actividades han establecido para sí mismas.</span><span class="sxs-lookup"><span data-stu-id="72460-108">Validation is performed to ensure that the workflow activities validate based on the rules that the activities have set for themselves.</span></span> <span data-ttu-id="72460-109">Si hay errores de validación, el compilador devuelve una lista.</span><span class="sxs-lookup"><span data-stu-id="72460-109">If there are validation errors, the compiler returns a list of the errors.</span></span>  
- <span data-ttu-id="72460-110">Se genera una clase parcial a partir de la definición de marcado que se introduce en el compilador.</span><span class="sxs-lookup"><span data-stu-id="72460-110">A partial class is generated from the markup definition that is input into the compiler.</span></span>  

- <span data-ttu-id="72460-111">El código se genera para ayudar en la ejecución del motor de tiempo de ejecución de las actividades.</span><span class="sxs-lookup"><span data-stu-id="72460-111">Code is generated to help with the run-time execution of the activities.</span></span> <span data-ttu-id="72460-112">Se generan suscripciones a los eventos, que ayudan a las actividades a saber cuándo ha finalizado la ejecución de las actividades que contienen.</span><span class="sxs-lookup"><span data-stu-id="72460-112">Event subscriptions are generated, which help activities know when the activities they contain are finished executing.</span></span>  
- <span data-ttu-id="72460-113">Las clases parciales generadas a partir del archivo de marcado y las clases parciales del archivo de código se introducen en el compilador de .NET Framework C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="72460-113">The partial classes generated from the markup file and the partial classes from the code file are entered into the .NET Framework C# or Visual Basic compiler.</span></span> <span data-ttu-id="72460-114">El resultado de este proceso es el ensamblado de .NET, WorkflowSample.dll.</span><span class="sxs-lookup"><span data-stu-id="72460-114">The output of this process is the .NET assembly, WorkflowSample.dll.</span></span> <span data-ttu-id="72460-115">Se puede implementar para ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72460-115">This can be deployed to run the workflow.</span></span>

### <a name="compiler-options"></a><span data-ttu-id="72460-116">Opciones del compilador</span><span class="sxs-lookup"><span data-stu-id="72460-116">Compiler options</span></span>

<span data-ttu-id="72460-117">En esta sección se muestran las opciones del compilador de línea de comandos de wfc.exe Workflow.</span><span class="sxs-lookup"><span data-stu-id="72460-117">This section shows the options for the wfc.exe workflow command-line compiler.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="72460-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72460-118">Remarks</span></span>
> [!NOTE]
> <span data-ttu-id="72460-119">En esta documentación se describen los tipos y espacios de nombres que están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="72460-119">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="72460-120">Normalmente, en el archivo *wfc.exe.config* se define una lista de tipos autorizados.</span><span class="sxs-lookup"><span data-stu-id="72460-120">A list of authorized types is usually defined in the *wfc.exe.config* file.</span></span> <span data-ttu-id="72460-121">Durante la fase de validación de la compilación del flujo de trabajo, se rechaza un documento de origen del flujo de trabajo si éste o el archivo de reglas complementario hacen referencia directamente a cualquier tipo de .NET Framework que no esté presente en una lista de tipos autorizados.</span><span class="sxs-lookup"><span data-stu-id="72460-121">During the validation phase of workflow compilation, a workflow source document is rejected if it or the companion rules file directly references any .NET Framework types not present in a list of authorized types.</span></span> <span data-ttu-id="72460-122">La lista de tipos autorizados es un documento XML donde cada entrada indica un `Assembly` , un `Namespace` , un `TypeName` y un `True` indicador {&#124;`False` } autorizado.</span><span class="sxs-lookup"><span data-stu-id="72460-122">The list of authorized types is an XML document where each entry indicates an `Assembly`, a `Namespace`, a `TypeName`, and an Authorized {`True`&#124;`False`} indicator.</span></span> <span data-ttu-id="72460-123">`AuthorizedType` corresponde a una entrada de la lista.</span><span class="sxs-lookup"><span data-stu-id="72460-123">`AuthorizedType` corresponds to an entry in the list.</span></span> <span data-ttu-id="72460-124">Se permiten las designaciones de caracteres comodín, que se pueden usar para incluir o excluir espacios de nombres completos.</span><span class="sxs-lookup"><span data-stu-id="72460-124">Wildcard character designations, which can be used to include or exclude complete namespaces, are allowed.</span></span> <span data-ttu-id="72460-125">Por ejemplo, `Type="System.*"` incluye todos los tipos en <xref:System> , incluidos los tipos contenidos en los espacios de nombres secundarios.</span><span class="sxs-lookup"><span data-stu-id="72460-125">For example, `Type="System.*"` includes all types in <xref:System>, including types contained in child namespaces.</span></span>
  
<span data-ttu-id="72460-126">El uso de una lista de tipos autorizados se controla mediante la <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> opción `'/checktypes'` .</span><span class="sxs-lookup"><span data-stu-id="72460-126">The use of a list of authorized types is controlled by the <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> option `'/checktypes'`.</span></span>

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
> <span data-ttu-id="72460-127">Cuando el `Type="System.*"` tipo está presente, es posible incluir otros tipos no deseados, como `Type="System.Configuration"` , para la compilación.</span><span class="sxs-lookup"><span data-stu-id="72460-127">When `Type="System.*"` type is present, it's possible to include other unintended types, such as `Type="System.Configuration"`, for compilation.</span></span> <span data-ttu-id="72460-128">Tenga cuidado y revise cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="72460-128">You should be cautious and review each one.</span></span> <span data-ttu-id="72460-129">Para cualquier tipo que se deba restringir, asegúrese de establecer `Authorized` en `False` .</span><span class="sxs-lookup"><span data-stu-id="72460-129">For any type that should be restricted, be sure to set `Authorized` to `False`.</span></span>

## <a name="see-also"></a><span data-ttu-id="72460-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="72460-130">See also</span></span>

- [<span data-ttu-id="72460-131">Clase AuthorizedType</span><span class="sxs-lookup"><span data-stu-id="72460-131">AuthorizedType class</span></span>](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
