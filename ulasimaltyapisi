import java.util.Arrays;

public class UretimPlanlama {

    // İşlem süreleri (islemSuresi[i][j]: i'inci işin j'inci makinede yapılma süresi)
    static int[][] islemSuresi;

    // Geçiş maliyetleri (gecisMaliyeti[i][j]: i'inci makinadan j'inci makineye geçiş maliyeti)
    static int[][] gecisMaliyeti;

    public static void minimumToplamSureVeYol(int isSayisi, int makineSayisi) {
        int[][] dp = new int[isSayisi][makineSayisi];
        int[][] oncekiMakine = new int[isSayisi][makineSayisi]; // Hangi makinadan geldiğini tutuyoruz

        // İlk iş için sadece işlem sürelerini alıyoruz
        for (int makine = 0; makine < makineSayisi; makine++) {
            dp[0][makine] = islemSuresi[0][makine];
            oncekiMakine[0][makine] = -1; // ilk iş olduğu için önceki makine yok
        }

        // Diğer işler için dinamik programlama
        for (int is = 1; is < isSayisi; is++) {
            for (int makine = 0; makine < makineSayisi; makine++) {
                dp[is][makine] = Integer.MAX_VALUE;
                for (int onceki = 0; onceki < makineSayisi; onceki++) {
                    int toplamSure = dp[is-1][onceki] + gecisMaliyeti[onceki][makine] + islemSuresi[is][makine];
                    if (toplamSure < dp[is][makine]) {
                        dp[is][makine] = toplamSure;
                        oncekiMakine[is][makine] = onceki;
                    }
                }
            }
        }

        // Son işte minimum toplam süreyi ve son makineyi bul
        int minimumSure = Integer.MAX_VALUE;
        int sonMakine = -1;
        for (int makine = 0; makine < makineSayisi; makine++) {
            if (dp[isSayisi-1][makine] < minimumSure) {
                minimumSure = dp[isSayisi-1][makine];
                sonMakine = makine;
            }
        }

        // Hangi makinelerin kullanıldığını bulmak için geriye doğru iz sür
        int[] secilenMakineler = new int[isSayisi];
        int isIndex = isSayisi - 1;
        while (isIndex >= 0) {
            secilenMakineler[isIndex] = sonMakine;
            sonMakine = oncekiMakine[isIndex][sonMakine];
            isIndex--;
        }

        // Sonuçları yazdır
        System.out.println("Minimum toplam süre: " + minimumSure);
        System.out.println("İşlerin makine seçimi:");
        for (int i = 0; i < isSayisi; i++) {
            System.out.println((i+1) + ". iş -> " + (secilenMakineler[i]+1) + ". makine");
        }
    }

    public static void main(String[] args) {
        int isSayisi = 3; // iş sayısı
        int makineSayisi = 2; // makine sayısı

        // Örnek işlem süreleri
        islemSuresi = new int[][] {
                {4, 6},
                {5, 7},
                {8, 3}
        };

        // Örnek geçiş maliyetleri
        gecisMaliyeti = new int[][] {
                {0, 2},
                {3, 0}
        };

        minimumToplamSureVeYol(isSayisi, makineSayisi);
    }
}
