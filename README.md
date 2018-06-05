# Domaci2

package example.domacidva.domaci2;

import android.content.Intent;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        /*Inicijalizacija dugmadi*/
        findViewById(R.id.imageButtonAudi).setOnClickListener(this);
        findViewById(R.id.buttonNaruci).setOnClickListener(this);

    }

    public void onClick(View v){

        switch (v.getId()){

            /*Pozivanje web strane na klik, koristeci implicitni intent*/
            case R.id.imageButtonAudi:
                Intent iWebAudi = new Intent(Intent.ACTION_VIEW, Uri.parse("http://www.audi.rs/"));
                startActivity(iWebAudi);
                break;

            /*Otvaranje novog activity-ja na klik, koristeci eksplicitni intent*/
            case R.id.buttonNaruci:
                Intent iIzborModela = new Intent(this, IzborModelaActivity.class);
                startActivity(iIzborModela);
                break;
        }

    }
}
