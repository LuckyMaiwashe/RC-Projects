# RC-Projects
This will serve as a library storing all my Rosebank College Projects Failed and successful, to help track my journey in Mobile Application and Web Development.
## LInk to Video Presentation of The Virtual Pet App
(https://youtu.be/-Js_wbyygvk)

### MainActivity.kt for the Login Page of the Virtual pet app we werre instructed to create.
package com.example.trainingleo20

import android.graphics.Color
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material3.Button
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableIntStateOf
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.painter.Painter
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.trainingleo20.ui.theme.TrainingLeo20Theme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            TrainingLeo20Theme {
                TrainingLeo20()
            }
        }
    }
}
@Composable
fun TrainingLeo20( modifier: Modifier = Modifier) {
    var showContent by remember { mutableStateOf(false) }
    var petImageId by remember { mutableIntStateOf(R.drawable.welcome__to) }
    var clean by remember { mutableIntStateOf(0) }
    var eat by remember { mutableIntStateOf(0) }
    var play by remember { mutableIntStateOf(0) }

    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        if (!showContent) {

        }

        val petImage: Painter = painterResource(petImageId)
        Text(
            text = "Hi, I'm Leo",
            fontSize = 30.sp,
            fontWeight = FontWeight.Bold
        )
        Image(
            painter = petImage,
            contentDescription = "Pet Image",
            modifier = Modifier
                .size(200.dp)
                .clip(shape = CircleShape)
        )

        Spacer(modifier = Modifier.padding(16.dp))

        if (showContent) {
            Column(
                verticalArrangement = Arrangement.Center
            ) {
                Button(onClick = {
                    petImageId = R.drawable.leo_eating
                    eat += 20
                    if (eat > 100) eat = 100
                }) {
                    Text(text = "Feed")
                }
                Box(
                    modifier = Modifier
                        .size(80.dp)
                        .background(color = androidx.compose.ui.graphics.Color.Blue)
                ) {
                    Text(
                        text = "$eat%",
                        modifier = Modifier.align(Alignment.Center)
                    )
                }
                Spacer(modifier = Modifier.height(16.dp))

                Column {
                    Button(onClick = {
                        petImageId = R.drawable.leo_standing
                        clean += 20
                        if (clean > 100) clean = 100
                    }) {
                        Text(text = "Clean")
                    }
                    Box(
                        modifier = Modifier
                            .size(80.dp)
                            .background(color = androidx.compose.ui.graphics.Color.Blue)
                    ) {
                        Text(
                            text = "$clean%",
                            modifier = Modifier.align(Alignment.Center)
                        )
                    }
                }
                Spacer(modifier = Modifier.height(16.dp))

                Button(onClick = {
                    petImageId = R.drawable.leo_dress_up
                    play += 20
                    if (play > 100) play = 100
                }) {
                    Text(text = "Playing")
                }
                Box(
                    modifier = Modifier
                        .size(80.dp)
                        .background(color = androidx.compose.ui.graphics.Color.Blue)
                ) {
                    Text(
                        text = "$play%",
                        modifier = Modifier.align(Alignment.Center)
                    )
                }
            }
        } else {
            Button(
                onClick = { showContent = true },
                modifier = Modifier.padding(horizontal = 16.dp)
            ) {
                Text(text = "START")
            }
        }

    }

    @Preview(showBackground = true)
    @Composable
    fun GreetingPreview() {
        TrainingLeo20Theme {
            TrainingLeo20()
        }
    }
}
