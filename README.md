# RC-Projects
This will serve as a library storing all my Rosebank College Projects Failed and successful, to help track my journey in Mobile Application and Web Development.
## MainActivity.kt for the Login Page of the Virtual pet app we werre instructed to create.
package com.example.trainingleo

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Button
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import com.example.trainingleo.ui.theme.TrainingLeoTheme


class LoginActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            TrainingLeoTheme {
                TrainingLeoLg()
            }
        }
    }
}


@Composable
fun TrainingLeoLg(modifier: Modifier = Modifier) {

    Column (
        modifier = Modifier.fillMaxSize(),
        horizontalAlignment = Alignment.CenterHorizontally

    ){
        val welcomeImage = painterResource(R.drawable.welcome__to)
        var login by remember {
            mutableStateOf("")
        }

        Text(text = "Welcome To Training Leo")
        Image(
            painter = welcomeImage,
            contentDescription = null,
            modifier = Modifier
                .fillMaxWidth()
                .height(450.dp)
        )
        Spacer(modifier = Modifier.padding(16.dp))

        Button(onClick = {
            login = ""
        }) {
            Text(text = "Start")
        }


    }
}


@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    TrainingLeoTheme {
        TrainingLeoLg()
    }
}

### SecondActivity.kt for the Main Page of the Virtual Pet App.
package com.example.trainingleo

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Button
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import com.example.trainingleo.ui.theme.TrainingLeoTheme


class LoginActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            TrainingLeoTheme {
                TrainingLeoLg()
            }
        }
    }
}


@Composable
fun TrainingLeoLg(modifier: Modifier = Modifier) {

    Column (
        modifier = Modifier.fillMaxSize(),
        horizontalAlignment = Alignment.CenterHorizontally

    ){
        val welcomeImage = painterResource(R.drawable.welcome__to)
        var login by remember {
            mutableStateOf("")
        }

        Text(text = "Welcome To Training Leo")
        Image(
            painter = welcomeImage,
            contentDescription = null,
            modifier = Modifier
                .fillMaxWidth()
                .height(450.dp)
        )
        Spacer(modifier = Modifier.padding(16.dp))

        Box {
            Button(onClick = {
                run { SecondActivity }
            }) {
                Text(text = "Start")
            }
        }


    }
}


@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    TrainingLeoTheme {
        TrainingLeoLg()
    }

}





