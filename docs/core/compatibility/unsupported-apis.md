---
title: API no admitidas en .NET Core
titleSuffix: ''
description: Obtenga información sobre qué API de .NET Framework siempre producen una excepción en .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: bd3516d9480ef42b6ea89825ba64867a3ca104e3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242951"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="7f03f-103">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="7f03f-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="7f03f-104">Las siguientes API siempre producirán una <xref:System.PlatformNotSupportedException> en .NET Core en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="7f03f-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="7f03f-105">En este artículo se organizan los miembros de API afectados por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7f03f-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7f03f-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7f03f-106">This article is a work-in-progress.</span></span> <span data-ttu-id="7f03f-107">No es una lista completa de las API que producen excepciones en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7f03f-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="7f03f-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que se inician en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7f03f-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="7f03f-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="7f03f-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="7f03f-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="7f03f-110">System</span></span>

| <span data-ttu-id="7f03f-111">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-111">Member</span></span> | <span data-ttu-id="7f03f-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-113">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-114">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="7f03f-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="7f03f-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-117">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="7f03f-118">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7f03f-119">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7f03f-120">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-121">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-122">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="7f03f-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="7f03f-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="7f03f-124">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-124">Member</span></span> | <span data-ttu-id="7f03f-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-126">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-127">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-128">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="7f03f-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="7f03f-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="7f03f-130">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-130">Member</span></span> | <span data-ttu-id="7f03f-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-132">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-133">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-134">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="7f03f-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="7f03f-135">System.Configuration</span></span>

| <span data-ttu-id="7f03f-136">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-136">Member</span></span> | <span data-ttu-id="7f03f-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="7f03f-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="7f03f-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="7f03f-139">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="7f03f-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="7f03f-140">System.Console</span></span>

| <span data-ttu-id="7f03f-141">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-141">Member</span></span> | <span data-ttu-id="7f03f-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="7f03f-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-143">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-145">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-147">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-149">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="7f03f-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7f03f-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-154">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="7f03f-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7f03f-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-156">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-158">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-160">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-162">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="7f03f-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="7f03f-165">System.Data.Common</span></span>

| <span data-ttu-id="7f03f-166">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-166">Member</span></span> | <span data-ttu-id="7f03f-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="7f03f-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="7f03f-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="7f03f-169">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="7f03f-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7f03f-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="7f03f-171">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-171">Member</span></span> | <span data-ttu-id="7f03f-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="7f03f-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-174">Linux</span><span class="sxs-lookup"><span data-stu-id="7f03f-174">Linux</span></span> |
| <span data-ttu-id="7f03f-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-176">Linux</span><span class="sxs-lookup"><span data-stu-id="7f03f-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="7f03f-177">macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="7f03f-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="7f03f-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="7f03f-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="7f03f-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="7f03f-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-183">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-185">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="7f03f-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7f03f-187">macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-187">macOS</span></span> |
| <span data-ttu-id="7f03f-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="7f03f-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="7f03f-190">System.IO</span></span>

| <span data-ttu-id="7f03f-191">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-191">Member</span></span> | <span data-ttu-id="7f03f-192">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-193">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-194">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="7f03f-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="7f03f-195">System.IO.Pipes</span></span>

| <span data-ttu-id="7f03f-196">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-196">Member</span></span> | <span data-ttu-id="7f03f-197">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="7f03f-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="7f03f-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7f03f-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7f03f-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-201">Linux and macOS</span></span> |
| <span data-ttu-id="7f03f-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="7f03f-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="7f03f-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="7f03f-205">System.Media</span></span>

| <span data-ttu-id="7f03f-206">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-206">Member</span></span> | <span data-ttu-id="7f03f-207">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-208">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="7f03f-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="7f03f-209">System.Net</span></span>

| <span data-ttu-id="7f03f-210">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-210">Member</span></span> | <span data-ttu-id="7f03f-211">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-212">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-213">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-214">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-215">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-216">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-217">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-218">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-219">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-220">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-221">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-222">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="7f03f-223">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-224">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-225">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-226">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-227">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-228">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="7f03f-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="7f03f-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="7f03f-230">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-230">Member</span></span> | <span data-ttu-id="7f03f-231">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="7f03f-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="7f03f-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="7f03f-233">System.Net.Sockets</span></span>

| <span data-ttu-id="7f03f-234">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-234">Member</span></span> | <span data-ttu-id="7f03f-235">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="7f03f-236">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-237">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="7f03f-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="7f03f-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="7f03f-239">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-239">Member</span></span> | <span data-ttu-id="7f03f-240">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="7f03f-241">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="7f03f-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="7f03f-242">System.Reflection</span></span>

| <span data-ttu-id="7f03f-243">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-243">Member</span></span> | <span data-ttu-id="7f03f-244">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-245">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-246">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-247">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-248">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="7f03f-249">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-250">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="7f03f-251">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="7f03f-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="7f03f-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="7f03f-253">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-253">Member</span></span> | <span data-ttu-id="7f03f-254">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="7f03f-255">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="7f03f-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="7f03f-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="7f03f-257">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-257">Member</span></span> | <span data-ttu-id="7f03f-258">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-259">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="7f03f-260">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-261">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-262">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="7f03f-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="7f03f-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="7f03f-267">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-267">Member</span></span> | <span data-ttu-id="7f03f-268">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="7f03f-269">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="7f03f-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="7f03f-270">System.Security</span></span>

| <span data-ttu-id="7f03f-271">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-271">Member</span></span> | <span data-ttu-id="7f03f-272">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="7f03f-273">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7f03f-274">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-275">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="7f03f-276">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7f03f-277">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="7f03f-278">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="7f03f-279">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="7f03f-280">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7f03f-281">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7f03f-282">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="7f03f-283">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-284">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="7f03f-285">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="7f03f-286">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="7f03f-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="7f03f-287">System.Security.Claims</span></span>

| <span data-ttu-id="7f03f-288">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-288">Member</span></span> | <span data-ttu-id="7f03f-289">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="7f03f-290">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-291">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="7f03f-292">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-293">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-294">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="7f03f-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="7f03f-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="7f03f-296">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-296">Member</span></span> | <span data-ttu-id="7f03f-297">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-298">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="7f03f-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="7f03f-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="7f03f-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="7f03f-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7f03f-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="7f03f-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="7f03f-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="7f03f-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="7f03f-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="7f03f-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="7f03f-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="7f03f-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7f03f-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7f03f-312">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="7f03f-313">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-314">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-315">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-316">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-317">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7f03f-318">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-319">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="7f03f-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-322">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-323">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7f03f-324">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-325">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="7f03f-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="7f03f-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="7f03f-327">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-327">Member</span></span> | <span data-ttu-id="7f03f-328">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="7f03f-329">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-330">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="7f03f-331">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="7f03f-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="7f03f-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="7f03f-333">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-333">Member</span></span> | <span data-ttu-id="7f03f-334">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-335">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-336">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-337">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-337">All</span></span> |
| <span data-ttu-id="7f03f-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="7f03f-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7f03f-339">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="7f03f-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="7f03f-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="7f03f-341">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-341">Member</span></span> | <span data-ttu-id="7f03f-342">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-343">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="7f03f-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="7f03f-344">System.Security.Policy</span></span>

| <span data-ttu-id="7f03f-345">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-345">Member</span></span> | <span data-ttu-id="7f03f-346">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-347">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="7f03f-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="7f03f-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="7f03f-349">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-349">Member</span></span> | <span data-ttu-id="7f03f-350">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="7f03f-351">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="7f03f-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="7f03f-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="7f03f-353">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-353">Member</span></span> | <span data-ttu-id="7f03f-354">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-355">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="7f03f-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="7f03f-356">System.Threading</span></span>

| <span data-ttu-id="7f03f-357">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-357">Member</span></span> | <span data-ttu-id="7f03f-358">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-359">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-360">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="7f03f-361">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="7f03f-362">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="7f03f-363">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="7f03f-364">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="7f03f-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="7f03f-365">System.Xml</span></span>

| <span data-ttu-id="7f03f-366">Member</span><span class="sxs-lookup"><span data-stu-id="7f03f-366">Member</span></span> | <span data-ttu-id="7f03f-367">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="7f03f-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-368">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-369">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7f03f-370">Todas</span><span class="sxs-lookup"><span data-stu-id="7f03f-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="7f03f-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f03f-371">See also</span></span>

- [<span data-ttu-id="7f03f-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="7f03f-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="7f03f-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="7f03f-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="7f03f-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="7f03f-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
