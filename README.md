# Ai-new-artboard
make a new artboard on adobe illustrator by a script

/* global app, $ */
function addArtboard() {
 var doc = app.activeDocument;
    var thisBoardIndex = doc.artboards.getActiveArtboardIndex();
    var thisBoard = doc.artboards[thisBoardIndex];
    var lastBoard = doc.artboards[doc.artboards.length - 1];
    var thisRect = thisBoard.artboardRect;
    var lastRect = lastBoard.artboardRect;
    
    var newBoard = doc.artboards.add(thisRect);
    var offsetH = 20;
    newBoard.artboardRect = [
        lastRect[2] + offsetH,
        lastRect[1],
        lastRect[2] + offsetH + (thisRect[2] - thisRect[0]),
        lastRect[3]
    ];
    
   
    doc.selection = null;
};
addArtboard(); 
