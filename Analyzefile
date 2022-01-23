//Array from Dami that has all of the values of everything
var a = //json file
var lastMove;
var points = 0;
var totalPoints = a.length;

var x5, y5, x6, y6, x7, y7, x8, y8, x9, y9, x10, y10, x11, y11, x12, y12, x13, y13, x14, y14, x15, y15, x16, y16;

function updatePositions(something){
    //We're feeding in one element of our big array, which is a smaller array that stores the infor for one frame
    x5 = something["keypoints"][5]["x"];
    y5 = something["keypoints"][5]["y"];
    x6 = something["keypoints"][6]["x"];
    y6 = something["keypoints"][6]["y"];
    x7 = something["keypoints"][7]["x"];
    y7 = something["keypoints"][7]["y"];
    x8 = something["keypoints"][8]["x"];
    y8 = something["keypoints"][8]["y"];
    x9 = something["keypoints"][9]["x"];
    y9 = something["keypoints"][9]["y"];
    x10 = something["keypoints"][10]["x"];
    y10 = something["keypoints"][10]["y"];
    x11 = something["keypoints"][11]["x"];
    y11 = something["keypoints"][11]["y"];
    x12 = something["keypoints"][12]["x"];
    y12 = something["keypoints"][12]["y"];
    x13 = something["keypoints"][13]["x"];
    y13 = something["keypoints"][13]["y"];
    x14 = something["keypoints"][14]["x"];
    y14 = something["keypoints"][15]["y"];
    x15 = something["keypoints"][15]["x"];
    y15 = something["keypoints"][15]["y"];
    x16 = something["keypoints"][16]["x"];
    y16 = something["keypoints"][16]["y"];
    
}
function getsPoint(something){
    updatePositions(something);
    //One issue that we're going to have is that if you do the right move to the wrong section you'll still get a point but I don't know how to avoid that
    if(lastMove !== "fWr" && firstWorkoutRight()){
        points++;
    } else if (lastMove !== "fWl" && firstWorkoutLeft()){
        points++;
    } else if(lastMove !== "sWl" && secondWorkoutLeft()){
        points++;
    } else if(lastMove !== "sWr" && secondWorkoutRight()){
        points++;
    } else if(lastMove !== "tWl" && thirdWorkoutLeft()){
        points++;
    } else if(lastMove !== "tWr" && thirdWorkoutRight()){
        points++;
    }
}
function firstWorkoutRight(){
        //Left arm is correct (pointing up and right)
        if(y6 > y8 && y8 > y10 && x10 > x8 && x8 > x6){
            //Right arm is correct (elbow under wrist under shoulder)
            if(7 < 9 && 9 < 5){
                //Legs are apart (difference between knees is less than difference between ankles)
                if((x13-x14) < (x15-x16)){
                    lastMove = "fWr"
                    return true;
                }
            }
        }
        else{
            return false;
        }
}
function firstWorkoutLeft(){
    if(y5 > y7 && y7 > y9 && x9 < x7 && x7 < x5){
        if(8 < 10 && 10 < 6){
            if((x13-x14) < (x15-x16)){
                lastMove = "fWr"
                return true;
            }
        }
    }
    else{
        return false;
    }
        
}
function secondWorkoutLeft(){
    //Left elbow below left shoulder
    //Right elbow above left elbow
    //Right wrist above right elbow
    //Right hip < Right shoulder in x direction
    if(y8>y6 && y7<y8 && y9 < y7 && x11 < x5){
        lastMove = "sWl";
        return true;
    } else { 
        return false; 
    }

}
function secondWorkoutRight(){
    //Right elbow below right shoulder
    //Left elbow above right elbow
    //Left wrist above left elbow
    //Left hip greater than left shoulder in x direction
    if(y7>y5 && y8<y7 && y10<y8 && x12>x6){
        lastMove = "sWr";
        return true;
    } else { 
        return false; 
    }
}
function thirdWorkoutLeft(){
    //wrists above elbows above shoulders and left ankle above right knee
    if(y9<y7 && y7<y5 && y10<y8 && y8<y6 && y16 >y13){
        lastMove = "tWl";
        return true;
    }
    else{
        return false;
    }
    
}
function thirdWorkoutRight(){
    //wrists above elbows above shoulders
    //right ankle above left knee
    if(y9<y7 && y7<y5 && y10<y8 && y8<y6 && y15 > y14){
        lastMove = "tWr";
        return true;
    } else {
        return false;
    }
}
a.forEach(getsPoint);
var score = "Your score is: " + (points/totalPoints)*100 + "%";
