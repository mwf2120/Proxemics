# Proxemics

PennController.ResetPrefix()

newTrial("Intro", 
    newText("intro", "<p><strong>Welcome to the Figure Game!</strong></p>")
        .css("font-size", "2.0em")
        .css("text-align", "center")
        .settings.center()
        .print()
    ,
    newText("description", "In this game you will drag and drop the figures to different locations on the screen.</p>")
        .css("font-size", "1.5em")
        .css("text-align", "center")
        .settings.center()
        .print()
    ,
        newText("id_prompt", "Enter Participant ID:")
        .center()
        .css("font-size", "1.5em")
        .print()
      ,
    newTextInput("idnum")
        .center()
        .log("final")
        .lines(1)
        .print()
    ,
    newText("<p></p>")
        .center().print()
    ,
    newButton("submit", "Submit")
        .css("font-size", "1.5em")
        .center()
        .print()
        .wait(
            getButton("submit").test.clicked()
            .and(getTextInput("idnum").testNot.text("")
                    .failure(
                        newText("error", "<p>Please enter the participant's ID.</p>")
                            .center()
                            .css("font-size", "1.0em")
                            .color("red")
                            .print() 
                        )
                    .success(
                        newVar("subjID")
                            .global()
                            .set(getTextInput("idnum"))
                        )
                )
            )
    ,
    clear()
    ).log("id", getVar("subjID"))

newTrial("Set_1",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("woman", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("boy", "boy_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("woman"))
       .addDrag(getImage("boy"))
       .addDrop(getCanvas("grid"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_2",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("man", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("boy", "boy_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("man"))
       .addDrag(getImage("boy"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_3",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("rec_1", "rec_one_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_2", "rec_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_3", "rec_three_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("rec_1"))
       .addDrag(getImage("rec_2"))
       .addDrag(getImage("rec_3"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_4",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("man", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("woman", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("boy", "boy_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("man"))
       .addDrag(getImage("woman"))
       .addDrag(getImage("boy"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_5",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("man", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("woman", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("dog", "dog_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("man"))
       .addDrag(getImage("woman"))
       .addDrag(getImage("dog"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

//Missing trial 6 (square, circle, and triangle)

newTrial("Set_7",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("man", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("woman", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_one", "rec_one_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_two", "rec_one_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("man"))
       .addDrag(getImage("woman"))
       .addDrag(getImage("rec_one"))
       .addDrag(getImage("rec_two"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_8",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("woman_one", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("woman_two", "woman_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_one", "rec_one_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_two", "rec_one_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("woman_one"))
       .addDrag(getImage("woman_two"))
       .addDrag(getImage("rec_one"))
       .addDrag(getImage("rec_two"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Set_9",
    newCanvas("figlist", "72vw","58vh")
        .css("padding","1em")
        .color("lightgray")
        .print("left at 5vw", "middle at 50vh")
    ,
    newCanvas("grid", "72vw", "58vh")
        .css("padding", "1em")
        .color("yellow")
        .print("left at 20vw", "middle at 50vh")
    ,
    newSelector("figures")
    ,
    newImage("man_one", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("man_two", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("man_three", "man_two_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_one", "rec_one_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_two", "rec_one_small.png").selector("figures").print(getCanvas("figlist")),
    newImage("rec_three", "rec_one_small.png").selector("figures").print(getCanvas("figlist"))
    ,
    getSelector("figures").shuffle()
    ,
    newDragDrop("dd")
       .addDrag(getImage("man_one"))
       .addDrag(getImage("man_two"))
       .addDrag(getImage("man_three"))
       .addDrag(getImage("rec_one"))
       .addDrag(getImage("rec_two"))
       .addDrag(getImage("rec_three"))
       .addDrop(getCanvas("figlist"))
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("Task_2",
    newText("intro_2", "<p><strong>Great job! Let's play another game!<strong><p>")
        .css("font-size", "2.0em")
        .css("text-align", "center")
        .settings.center()
        .print()
    ,
    newButton("Continue").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Instructions_2", 
    newText("intro_two_cont", "In this game you will see sets of figures on the screen. Then, they will disappear and reappear at the bottom. Drag and drop the figures to the locations they appeared originally.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Let's practice!").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Instructions_3", 
    newText("intro_three", "Great job! One more game with these figures.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Next!").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Instructions_3_1", 
    newText("intro_three_cont", "This time you will see pairs of figures on the screen. After a bit of time, they will disappear. Then, different figures will appear on the screen. Place the new figures exactly where the original ones appeared.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newTimer(7000).start()
    .wait()
)

newTrial("Instructions_3_2", 
    newText("intro_three_cont_1", "For example, you might see a woman, man, and boy figure on the screen. After they dissapear, three more figures will appear but this time they may be three rectangles. The goal is to place the new figures in the exact locations that the original ones had been.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Let's practice!").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Task_4", 
    newText("intro_four", "Great job! Let's go on to the last game.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Next!").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Instructions_4", 
    newText("intro_four", "In this game you will see a circle with a figure in the middle. I'd like you to imagine that you are the figure in the middle of a circular room.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Next").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Instructions_4_1", 
    newText("intro_4_cont_1", "In each trial a figure will appear on the perimeter of the room with an identity of either 'friend' or 'stranger'. You will also see a dotted line between you, in the middle of the circle/room, and the figure. Please mark the location on the dotted line that you would begin to feel uncomfortable with the figure's location or proximity.")
    .css("font-size", "1.5em")
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Next").print("center at 50vw", "bottom at 99vh")
    .wait()
)

newTrial("Room",
    newText("This is what your room looks like, and that is you in the middle!")
        .settings.center()
        .print()
    ,
    newImage("center_image", "CID_center.png")
        .settings.center()
        .print()
        .wait()
)

newTrial("Stranger_Friend",
    newText("You will see a 'stranger' or 'friend' identifier like the one below.")
        .css("font-size", "2.0em")
        .center()
        .settings.center()
        .print()
    ,
    newText("<p><strong>Stranger</strong></p")
        .css("font-size", "2.5em")
        .css("text-align", "center")
        .settings.center()
        .print("center at 50%", "bottom at 50%")
        .wait()
)

newTrial("Fix_Point",
    newText("Then, you will see a screen that looks like this:")
        .settings.center()
        .print()
    ,
    newImage("fix", "fix_point.png")
    ,
    newCanvas("fixation_canvas"
        .center()
        .add("center at 50%", "bottom at 50%"), getImage("fix"))
        .print()
        .wait()
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("CID",
    newText("You will see figures at different locations around the perimeter of the circle. If the previous screen read 'stranger', I'd like you to imagine that the figure is a stranger. If the previous screen read 'friend', I'd like you to imagine that the figure is a friend.")
        .css("text-align", "center")
        .settings.center()
        .print()
    ,
    newImage("cid3", "CID3.png")
    ,
    newCanvas("canvas_1"
        .center()
        .add("center at 50%", "bottom at 50%"), getImage("cid3"))
        .print()
        .wait()
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("CID_1",
    newText("In each trial imagine that the figure is approaching you along the grey dotted line. Using the cursor, click the location on the dotted grey line that you would begin to feel uncomfortable with the figure's location.")
        .css("text-align", "center")
        .settings.center()
        .print()
    ,
    newImage("cid3", "CID3.png")
    ,
    newCanvas("canvas_2"
        .center()
        .add("center at 50%", "bottom at 50%"), getImage("cid_3"))
        .print()
        .wait()
    ,
    newTimer(5000).start()
    .wait()
)

newTrial("CID_2", 
    newText("You will have up to three seconds to select a location on the grey line. Once you click on the grey line, the next trial will begin. Are you ready to start?")
    
    .css("text-align", "center")
    .settings.center()
    .print()
    ,
    newButton("Continue to the game.").print("center at 50vw", "bottom at 99vh")
    .wait()
)


newTrial("sorf",
    newText("text", "<p><strong>Stranger</strong></p")
        .css("font-size", "4.0em")
        .css("text-align", "center")
        .settings.center()
        .print("center at 50%", "bottom at 50%")
    ,
    newTimer(1000).start()
        .wait()
    ,
    getText("text")
        .remove()
    ,
    newImage("fix", "fix_point.png")
        .print("center at 50%", "bottom at 50%"), getImage("fix")
        .wait()
    ,
    newTimer("Timer1",1000).start()
    .wait()
)

newTrial("sorf",
    newText("text", "<p><strong>Friend</strong></p")
        .css("font-size", "4.0em")
        .css("text-align", "center")
        .settings.center()
        .print("center at 50%", "bottom at 50%")
    ,
    newTimer(1000).start()
        .wait()
    ,
    getText("text")
        .remove()
    ,
    newImage("fix", "fix_point.png")
        .print("center at 50%", "bottom at 50%"), getImage("fix")
        .wait()
    ,
    newTimer("Timer1",1000).start()
    .wait()
)

//randomize friend or stranger ("sorf")
//not sure if the below works, but then need to randomize "cid", making sure each cycles through as both F and S

newTrial("cid",
    newImage("cid1", "CID1.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid3", "CID3.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid4.5", "CID4.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid4.5", "CID4.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid6", "CID6.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid7.5", "CID7.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid9", "CID9.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid10.5", "CID10.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid10.5", "CID10.5.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)

newTrial("cid",
    newImage("cid12", "CID12.png")
        .center()
        .print()
        .wait()
    ,
    newTimer(3000).start()
)
