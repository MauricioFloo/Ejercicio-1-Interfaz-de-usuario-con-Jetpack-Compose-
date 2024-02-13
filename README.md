# Ejercicio-1-Interfaz-de-usuario-con-Jetpack-Compose


package com.example.ejercicio1

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.ejercicio1.ui.theme.Ejercicio1Theme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            Ejercicio1Theme {
                // A surface container using the 'background' color from the theme
                Surface(
                        modifier = Modifier.fillMaxSize(),
                        color = MaterialTheme.colorScheme.background
                ) {
                    CertificateCourse("Mauricio Flores Pradel")
                }
            }
        }
    }
}

@Composable
fun CertificateCourse(name: String, modifier: Modifier = Modifier) {

    Column (
       modifier = modifier
           .fillMaxSize()
           .padding(10.dp),
       verticalArrangement = Arrangement.Center

       ){
        Row (
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(40.dp)
        ){
            Image(painter = painterResource(id = R.drawable.logounam),
                contentDescription = null,
                modifier = modifier.size(50.dp)
            )
            Text(text = "\nDepartamento de Desarrollo", fontSize = 15.sp)
            Image(painter = painterResource(id = R.drawable.escudo_fi_color),
                contentDescription = null,
                modifier = modifier.size(50.dp)
            )

        }


       Text(
           text = "\n\nThis certificate is presented to.",
           fontSize = 20.sp,
           textAlign = TextAlign.Center,
           modifier = modifier.fillMaxWidth()
       )
       Box(contentAlignment = Alignment.Center)
       {
           Image(
               painter = painterResource(id = R.drawable.android_3384009_640) ,
               contentDescription = null,
           modifier = modifier.fillMaxWidth(),
           alpha = 0.5f
           )

           Text(text = name,
               fontSize = 30.sp,
               fontWeight = FontWeight.Bold,
               textAlign = TextAlign.Center,
               modifier = modifier.fillMaxWidth()
           )
       }
       Text(
           text = "Has completed a 2 hours course on:",
           fontSize = 22.sp,

       )
       Text(
           text = "Android",
           fontSize = 25.sp,
           textAlign = TextAlign.Center,
           modifier = modifier.fillMaxWidth()
           )

        Row (
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(30.dp)
        ){
            Image(painter = painterResource(id = R.drawable.firmaleo),
                contentDescription = null,
                modifier = modifier.size(90.dp)
            )

            Image(painter = painterResource(id = R.drawable.firmacris),
                contentDescription = null,
                modifier = modifier.size(90.dp)
            )

        }
        Row (
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(17.dp)
        ){
            Text(text = "Lionel Messi", fontSize = 18.sp,fontWeight = FontWeight.Bold )
            Text(text ="Cristiano Ronaldo",fontSize = 18.sp,fontWeight = FontWeight.Bold)

        }
        Row (
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(20.dp)
        ){
            Text(text = "Representatives", fontSize = 15.sp)
            Text(text ="Representatives",fontSize = 15.sp)

        }

   }



}

@Preview(showBackground = true)
@Composable
fun CertificateCoursePreview() {
    Ejercicio1Theme() {
        CertificateCourse("Mauricio Flores Pradel")
    }
}
