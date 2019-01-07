# kotlin-study

bufferdReader -> Kotlin
ps -> http://kotlination.com/kotlin/read-file-kotlin

fun readURLs(url: String?): ArrayList<String>? {
        if (url == null) return null
        val allURls = ArrayList<String>()
        try {

            val urls = URL(url)
            val `in` = BufferedReader(
                InputStreamReader(
                    urls
                        .openStream()
                )
            )
            allURls.addAll(listOf(`in`.readLine()))
//            while ((str = `in`.readLine()) != null) {
//                allURls.add(str)
//            }
            `in`.close()
            return allURls
        } catch (e: Exception) {
            e.printStackTrace()
            return null
        }

    }
