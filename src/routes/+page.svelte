<script lang="ts">
    import Blockly from "blockly";
    import { onMount } from "svelte";

    const toolbox = {
        kind: "flyoutToolbox",
        contents: [
            {
                kind: "block",
                type: "controls_repeat_ext",
                inputs: {
                    TIMES: {
                        shadow: {
                            type: "math_number",
                            fields: {
                                NUM: 5,
                            },
                        },
                    },
                },
            },
        ],
    };

    onMount(() => {
        Blockly.inject("blocklyDiv", {
            toolbox: toolbox,
            scrollbars: false,
            horizontalLayout: true,
            toolboxPosition: "end",
        });
    });
</script>

<div id="blocklyDiv" />

<style>
    :global(html) {
        min-height: 100vh;
    }
    :global(body) {
        min-height: 100vh;
        background: red;
    }
    #blocklyDiv {
        width: 100%;
        height: 100%;
        position: absolute;
    }
</style>
