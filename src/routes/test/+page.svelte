<script>
    import {
        Button,
        Column,
        Grid,
        RadioTile,
        Row,
        Tile,
        TileGroup,
    } from "carbon-components-svelte";

    let answer = $state("");
</script>

<Grid>
    <Row>
        <Column sm={4} md={4} lg={8}>
            <h1>Question 1</h1>
            <br>
            <Tile>
                <p>
                    I prefer practical work to purely theoretical work.
                </p>
            </Tile>
        </Column>

        <Column sm={4} md={4} lg={8}>
            <TileGroup
                    legendText="Choose your answer"
                    name="answer"
                    bind:selected={answer}
            >
                <RadioTile value="strongly-agree">
                    Strongly agree
                </RadioTile>

                <RadioTile value="agree">
                    Agree
                </RadioTile>

                <RadioTile value="neutral">
                    Neutral
                </RadioTile>

                <RadioTile value="disagree">
                    Disagree
                </RadioTile>

                <RadioTile value="strongly-disagree">
                    Strongly disagree
                </RadioTile>
            </TileGroup>

            <Button
                    kind="primary"
                    disabled={!answer}
            >
                Next question
            </Button>
        </Column>
    </Row>
</Grid>

<style>
    :global(.bx--btn) {
        width: 100%;
        max-width: 100%;
        margin-top: 1rem;
    }
</style>