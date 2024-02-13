# Ejercicio-1-Interfaz-de-usuario-con-Jetpack-Compose
Ejercicio 1 temas selectos de programación
package mx.unam.fi.certificadocurso

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
import mx.unam.fi.certificadocurso.ui.theme.CertificadoCursoTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            CertificadoCursoTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    CertificateCourse("Alcántara Ortiz César Guillermo")
                }
            }
        }
    }
}

@Composable
fun CertificateCourse(name: String, modifier: Modifier = Modifier) {

    Column(
        modifier = modifier
            .fillMaxSize()
            .padding(10.dp),
        verticalArrangement = Arrangement.Center,
    ){
        Row(
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(40.dp)
        ){
            Image(
                painter = painterResource(id = R.drawable.logo_unam),
                contentDescription = null,
                modifier = modifier.size(50.dp)
            )
            Text(
                text = "\nDepartamento de desarrollo\n",
                fontSize = 15.sp
            )
            Image(
                painter = painterResource(id = R.drawable.escudo_fi_color),
                contentDescription = null,
                modifier = modifier.size(50.dp)
            )
        }
        Text(
            text ="This certificate is presented to:\n",
            fontSize = 20.sp,

            textAlign = TextAlign.Center,
            modifier = modifier.fillMaxWidth()

        )
        Box(contentAlignment = Alignment.Center){

            Image(
                painter = painterResource(id = R.drawable.android_logo),
                contentDescription = null,
                modifier =modifier.fillMaxWidth(),
                alpha = 0.4f
            )
            Text(
                text =name,
                fontSize = 30.sp,
                fontWeight = FontWeight.Bold,
                textAlign = TextAlign.Center,
                modifier = modifier.fillMaxWidth()

            )
        }
        Text(
            text = "Ha completado de manera exitosa 2 hrs del curso en Android",
            fontSize = 20.sp,

            textAlign = TextAlign.Center,
            modifier = modifier.fillMaxWidth()
            )

        Row(
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(30.dp)
        ){
            Image(
                painter = painterResource(id = R.drawable.firma_1),
                contentDescription = null,
                modifier = modifier.size(150.dp)
            )
            Image(
                painter = painterResource(id = R.drawable.firma_2),
                contentDescription = null,
                modifier = modifier.size(150.dp)
            )

        }
        Row(
            horizontalArrangement = Arrangement.SpaceBetween,
            modifier = modifier
                .fillMaxWidth()
                .padding(20.dp)
        ){
            Text(
                text = "Carlos Slim\n       AGL",
                fontSize = 18.sp,
            )
            Text(
                text = "Carlos Slim Jr.\n       AGL",
                fontSize = 18.sp,
            )

        }

    }

}

@Preview(showBackground = true)
@Composable
fun CertificateCoursePreview() {
    CertificadoCursoTheme {
        CertificateCourse("Alcántara Ortiz César Guillermo")
    }
}
