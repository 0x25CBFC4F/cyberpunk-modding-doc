# BlackboardSystem

<tldr>
This is a system that allows multiple game components to communicate values between each other without explicitly referencing each other.
</tldr>

## Retrieving the system

<tabs>
    <tab id="cet" title="CET">
        <code-block lang="javascript">
            Game.GetBlackboardSystem()
        </code-block>
    </tab>
    <tab id="redscript" title="Redscript">
        <code-block lang="swift">
            GameInstance.GetBlackboardSystem()
        </code-block>
    </tab>
</tabs>

## How blackboards are registered.

I'm pretty sure they're registered from the native code, which isn't really accessible to us from CET/Redscript.
Also, it looks like blackboards' Redscript code is auto-generated on compile-time.

## How does this system work?

[Blackboards explained](BlackboardsExplained.md)

## Methods

<tip>Behavior of local blackboards is unknown to me.</tip>

```Swift
Get(definition: ref<BlackboardDefinition>) → ref<IBlackboard>
```

Returns global blackboard (`IBlackboard`) for a definition.

```Swift
GetLocalInstanced(entityID: EntityID, definition: ref<BlackboardDefinition>) → ref<IBlackboard>
```

Returns a local blackboard for specific entity.

```Swift
RegisterLocalBlackboard(blackboard: ref<IBlackboard>) → Void
```

Registers a local blackboard.

```Swift
RegisterLocalBlackboardForDebugRender(blackboard: ref<IBlackboard>, debugName: String) → Void
```

Registers a local blackboard for viewing in some kind of debug menu. Unknown which one.
<include from="contribute.md" element-id="contribute" />

## Usage example

